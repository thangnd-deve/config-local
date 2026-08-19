# Nvim config

Nguồn: `~/dotfiles/.config/nvim` (LazyVim-based).

Không copy `lazy-lock.json` / `lazyvim.json` — các file này do `lazy.nvim` tự sinh, đừng chép tay.

## Restore

```bash
ln -s /path/to/this/nvim ~/.config/nvim
nvim   # lazy.nvim sẽ tự clone plugin, tạo lazy-lock.json mới
```

## Yêu cầu đi kèm

- Neovim >= 0.12 (`brew install neovim`) — `rustaceanvim` cần bản này trở lên.
- Node.js hoạt động được trong PATH của shell mặc định (xem `../fish/README.md`) — `copilot.lua` cần `node --version` chạy được.
