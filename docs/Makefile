# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line, and also
# from the environment for the first two.
SPHINXOPTS    ?=
SPHINXBUILD   ?= sphinx-build
SOURCEDIR     = .
BUILDDIR      = _build

TUT_DST_DIR := tutorials

NOTEBOOKS := \
	mstable_to_uvtable.rst \
	fitting_procedure.ipynb \
	prior_sensitivity.rst \
	fit_convergence.rst \
	model_limitations.rst \
	lognormal_fit.ipynb \
	mock_data.ipynb \
	AS209_clean_profile.txt \
	AS209_continuum.npz \

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

clean:
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile $(NOTEBOOK_TARGETS)

NOTEBOOK_TARGETS := $(patsubst %, $(TUT_DST_DIR)/%, $(NOTEBOOKS))



.PHONY: help Makefile

$(TUT_DST_DIR):
	mkdir -p $(TUT_DST_DIR)


# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
html: Makefile $(NOTEBOOK_TARGETS)
	@echo $(NOTEBOOK_TARGETS)
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
