---
title: "Simplified vim documentation"
date: 2022-07-01T09:49:47+03:00
draft: true
---

# A simplified vim documentation

	:noremap	Normal, Visual and Operator-pending
	:vnoremap	Visual
	:nnoremap	Normal
	:onoremap	Operator-pending
	:noremap!	Insert and Command-line
	:inoremap	Insert
	:cnoremap	Command-line

`|` use this as a separator while mapping and unmapping,
similar to how we use `;` to terminate a statement
	:map <Space> W|     " Use spacebar to move forward a word

to use space -> `use `<Space>`
