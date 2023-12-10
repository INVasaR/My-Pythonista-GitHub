# Необхідні глобальні змінні
	user_agents_list = [
    'Mozilla/5.0 (iPad; CPU OS 12_2 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Mobile/15E148',
    'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.83 Safari/537.36',
    'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.51 Safari/537.36']
	source_url = appex.get_url() if appex.get_url() != None else clipboard.get()

# Формулювання запитів
	r = requests.get(url, headers={'User-Agent': random.choice(user_agents_list)})

# Знаходить всі посилання з url і записує в файл

	def main():
		soup = BeautifulSoup(r.text, 'html5lib')
		f = open("urls.txt", "w")
		for link in soup.find_all("a") :
			data = link.get('href')
			f.write(data)
			f.write("\n")
		f.close()

# Завантаження картинок
	def download(name, url):
		data = requests.get(url, headers={'User-Agent': random.choice(user_agents_list)})
		f = open(name,'wb')
		f.write(data.content)
		f.close()
