cmake_minimum_required(VERSION 3.27)

project(3DMath
	VERSION 0.0.1
	LANGUAGES
	DESCRIPTION "Exercises for the book 'Mathematics for 3D Game Programming and Computer Graphics Third Edition'"
)

find_package(LATEX REQUIRED)

add_custom_target(solutions
	ALL
	pdflatex ${CMAKE_SOURCE_DIR}/docs/math.tex -output-directory=${CMAKE_BINARY_DIR}/docs
	DEPENDS docs/math.tex
	BYPRODUCTS docs/math.pdf
	SOURCES docs/math.tex
)
