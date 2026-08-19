# Fish config

Nguồn: `~/dotfiles/.config/fish`.

Không copy `functions/`, `completions/`, `conf.d/`, `fish_variables` — các file này do
fisher tự sinh lại từ `fish_plugins`, đừng chép tay.

## Restore

```bash
ln -s /path/to/this/fish ~/.config/fish
fish -c "curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher"
fish -c "fisher update"   # đọc fish_plugins, cài lại tide/z/fzf.fish/nvm.fish
```

## Node.js qua nvm.fish

Fish (shell mặc định của máy) không tự có `node` trong PATH — plugin `nvm.fish` lo việc
này, không phải Homebrew node (Homebrew node từng bị vỡ do lệch version `llhttp`).

Sau khi `fisher update` xong:

```bash
fish -c "nvm install 22.19.0"
fish -c "set -Ux nvm_default_version 22.19.0"
```

Mở shell interactive mới, `node --version` phải trả về đúng version — nếu không, `nvm
use --silent \$nvm_default_version` (trong `conf.d/nvm.fish`) chỉ chạy khi `status
is-interactive`, nên đừng test bằng `fish -c` (non-interactive), dùng `fish -ic` thay thế.
