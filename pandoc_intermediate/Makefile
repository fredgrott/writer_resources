# Directory with the markdown files. Defaults to "src"
SOURCEDIR ?= src
# Directory to output files. Defaults to "dist"
OUTDIR ?= dist
# Project name. Defaults to the name of working directory
PROJECT ?= $(shell basename `pwd`)

# Generate EPUB file
epub:
	pandoc -d config.yml \ 
     --include_in-header chapter_break.tex \
     --highlight-style pygments.theme \
     --include-in-header listings-setup.tex \
	`find $(SOURCEDIR) -name '*.md' | sort` \
     -V linkcolor:blue \
     -V geometry:a4paper \
     -V geometry:margin=2cm \
     -V mainfont="DejaVu Serif" \
     -V monofont="Space Mono" \
     --listings \
	-o $(OUTDIR)/$(PROJECT).epub


# Generate PDF file
pdf:
	pandoc -d config.yml \
     --include_in-header chapter_break.tex \
     --highlight-style pygments.theme \
     --include-in-header listings-setup.tex \
	`find $(SOURCEDIR) -name '*.md' | sort` \
     -V linkcolor:blue \
     -V geometry:a4paper \
     -V geometry:margin=2cm \
     -V mainfont="DejaVu Serif" \
     -V monofont="Space Mono" \
     --listings \
	-o $(OUTDIR)/$(PROJECT).pdf
