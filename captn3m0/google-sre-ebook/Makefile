.PHONY: help build clean

help:
	@cat $(firstword $(MAKEFILE_LIST))

build: \
	google-the-site-reliability-workbook.epub \
	google-the-site-reliability-workbook.mobi \
	google-the-site-reliability-workbook.pdf \
	google-the-site-reliability-workbook.epub.d

google-the-site-reliability-workbook.epub:
	docker run --rm --volume $(realpath .):/output -e BOOK_SLUG='srw_book' captn3m0/google-sre-ebook:latest

google-the-site-reliability-workbook.epub.d: google-the-site-reliability-workbook.epub
	unzip $< -d $@

clean:
	rm google-the-site-reliability-workbook.*
