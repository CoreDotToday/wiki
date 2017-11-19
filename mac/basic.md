<!-- TITLE: Mac Basic Commands -->
<!-- SUBTITLE: A quick summary of Basic -->

# Mac
- [Shortcut Key Mapping](/mac/shortcut)

# Bash Shell
## PDF2PNG
```
for i in *.pdf; do
  name=$i;
  name=${name%.*};
  sips -s format png -s dpiWidth 300 $i --out ${name}.png;
done
```