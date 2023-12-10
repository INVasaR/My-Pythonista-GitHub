# Отримання дати і часу
	d = datetime.datetime.now()
	date = datetime.date.today()
	time = d.strftime('%H:%M')

# Отримати url з Поширення або буферу обміну
	source_url = appex.get_url() if appex.get_url() != None else clipboard.get()
