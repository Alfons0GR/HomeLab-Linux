# Day 2 — vim, pipes, grep, chmod/chown

Rocky Linux 10.2 (`rocky01`). Work directory: `~/lab/day2`.

## What I practiced

- vim: `i`, `Esc`, `:wq`, `:q!`
- pipes `|` and redirects `>` / `>>`
- `grep`, `grep -n`, `grep -i`, `grep -v`, `grep -c`
- `chmod` 600 / 640 / 700
- `chown user:group` (needs `sudo`)
- Directories need execute (`x`) to `cd` into them

## Commands

```bash
mkdir -p ~/lab/day2
cd ~/lab/day2

vim notas.txt

echo -e "error disco\nok\nerror red\nok\nerror disco" > servicios.log
grep error servicios.log
grep error servicios.log > solo-errores.txt
grep -n error servicios.log
grep -i ERROR servicios.log
grep -v ok servicios.log
grep -c error servicios.log

chmod 600 notas.txt
sudo chown labuser:webteam servicios.log
sudo chown pipo:pipo servicios.log

mkdir privada
chmod 600 privada   # cd fails
chmod 700 privada   # cd works
