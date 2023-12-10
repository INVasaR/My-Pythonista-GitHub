# Шукає пусту клітинку і перевіряє попередню перед тим як шось записувати
	cv = 0
	x = 0
	while cv != None :
		x += 1
		cell = ws.cell(row=x, column=1)
		cv = cell.value
	cell = cell.offset(-1, 0)
	if cell.value != str(datetime.date.today()) :
		cell = cell.offset(1, 0)
		cell.value = str(datetime.date.today())
