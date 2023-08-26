emerge
---

#### sync

```
emerge-webrsync
emerge --sync
```

---

#### update `/etc`

```
etc-update --automode -3
```

---

#### update system

```
emerge -auvDN --with-bdeps=y --autounmask-write @world
```

<details>
<summary>continue update</summary>

```
emerge @preserved-rebuild
perl-cleaner --all
emerge -auvDN --with-bdeps=y --autounmask-write @world
```

</details>

---

#### install package (to @world)

```
emerge -av [package]
```

<details>

<summary>install package (temporary)</summary>

```
emerge -av --oneshot [package]
```

</details>

---

#### search

```
emerge --search [keyword]
```

<details>
<summary>search details</summary>

- search description

```
emerge --searchdesc [keyword]
```

- Search packages using a regular expression:

```
emerge -s '%^python$'
```

- List all packages in a category:

```
emerge -s '@net-ftp'
```

</details>

---

#### list packages installed
```
emerge --pretend --emptytree world
```
or
```
qlist -IRv
```

---

#### remove package
```

```

<details>
<summary>remove without clean dependencies</summary>

```
emerge --unmerge [package]
```

</details>
