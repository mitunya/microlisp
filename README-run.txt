
use interpreter example

(ql:quickload :microlisp)
(in-package :microlisp)

(load "macros/standard.lisp")
(include "includes/standard.ml")
(include "test/units.ml")
((1 inch) meter mm) ;; input
;; => ((0.0254 METER) (25.4 MM))


(compile-files "includes/standard.ml" "test/units.ml")
;; => create test/unit.c

% cc -g unit.c libruntime.a
% a.out
((1 INCH) MM) ; input
;; => ((127/5 MM))


