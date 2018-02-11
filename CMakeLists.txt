cmake_minimum_required(VERSION 3.0)

project(StoSi NONE)
include(UseLATEX)

add_custom_target(
	writegitid ALL
	COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/write-gitid.sh
	WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)

set(IMAGES
	img/Logo.pdf
	img/Binomial_cdf.pdf
	img/geometric_pmf.pdf
	img/normal_pdf.pdf
	img/Binomial_pmf.pdf
	img/kreuzlds.pdf
	img/poisson_cdf.pdf
	img/exponential_cdf.pdf
	img/lds.pdf
	img/poisson_pmf.pdf
	img/exponential_pdf.pdf
	img/Signalarten.pdf
	img/geometric_cdf.pdf
	img/normal_cdf.pdf
	img/cat.jpg
	img/SincInterp.png
	img/Gaussian_2D.png
)

add_latex_document(
  StochastischeSignale.tex
  FORCE_PDF
	IMAGES ${IMAGES}
	DEPENDS writegitid
)
