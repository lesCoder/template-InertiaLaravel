Template do setup do Inertia com Laravel

passos do zero:
1 - curl -s https://laravel.build/NomeDoApp | bash

2 - ./vendor/bin/sail up

3 - dentro do container rode:

    composer require inertiajs/inertia-laravel
  
4 - rode php artisan inertia:middleware

5 - registra no kernel web:

		\App\Http\Middleware\HandleInertiaRequests::class,
  
6 - instala no container o VUE

		npm install @inertiajs/vue3
  
7 - cria o diretório Pages dentro do diretório JS

		Neste diretório serão inseridos os arquivos em VUE
  
8 - instale no container 

		npm i @vitejs/plugin-vue
  
9 - Altere no arquivo vite.config.js adicionando na segunda linha 

		import vue from "@vitejs/plugin-vue";
  
add logo na inicialização de plugins
 
		vue(),
  
10 - na rota do Laravel alterar para algo assim para ter um exemplo


	Route::get('/', function () {
		return Inertia::render(
			'Home',
			[
				'title' => 'Oi oi Oi'
			]
		);
	});
 
11 - inicie a aplicação rodando no container

	npm run dev
