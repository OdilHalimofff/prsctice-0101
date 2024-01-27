#!/bin/bash

# Fayl nomi
filename="lorem_text.txt"

# Lorem Ipsum matni (bu yerda faqat bir nechta jumla keltirilgan, siz ko'proq matn qo'shishingiz mumkin)
lorem="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."

# Faylni yaratish va uni 10000 so'z bilan to'ldirish
for i in {1..1000}; do
    echo $lorem >> $filename
done

# Faylni 10000 so'zga qisqartirish (har bir so'zni alohida qatorga joylashtirish uchun)
cat $filename | tr ' ' '\n' | shuf | head -n 10000 | tr '\n' ' ' > $filename.tmp && mv $filename.tmp $filename

echo "Fayl yaratildi: $filename"

