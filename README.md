bclose.vim
==========

Delete a buffer without closing the window


http://vim.wikia.com/wiki/Deleting_a_buffer_without_closing_the_window

## Usage
The `:Bclose`command deletes a buffer without changing the window layout. For each window where the buffer is currently displayed:
*Show the alternate buffer (`:buffer #`), if any.
*Otherwise, show the previous buffer (`:bprevious`), if any.
*Otherwise, show an empty buffer.

;`:Bclose`
:Close buffer in current window.

;`:Bclose ''N''`
:Close buffer number ''N'' (as shown by `:ls`).

;`:Bclose ''Name''`
:Close buffer named ''Name'' (as shown by `:ls`).

Assuming the default backslash leader key, you can also press `\bd` to close (delete) the buffer in the current window (same as <code>:Bclose</code>).

Like the `:bdelete` command, `:Bclose` will fail if the buffer has been modified. You can append <code>!</code> to discard all changes (for example, <code>:Bclose!</code> will delete the buffer in the current window; any changes to the buffer are lost).

By default, `:Bclose` will close a buffer even if it is displayed in multiple windows (the windows are not closed). Put the following in your [[vimrc]] if you would prefer that a buffer is not closed if it is displayed more than once:

    :let bclose_multiple = 0
