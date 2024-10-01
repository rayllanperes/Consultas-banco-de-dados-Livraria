# Consultas-banco-de-dados-Livraria 

2.	Implemente uma consulta para listar o quantitativo de livros cadastrados, independentemente da editora.

Código utilizado:  

show databases; use livraria; show tables;  
 
select * from livro;  

select count(idLivro) from livro; 

Resultado da consulta: 

![image](https://github.com/user-attachments/assets/b5ec5d7f-293a-45a3-9b92-7b7ebeb12b84)

3.	Implemente uma consulta para listar o nome dos clientes cadastrados. A listagem deve ser mostrada em ordem crescente.

Código utilizado: 

use livraria; 

show tables; 
 
select * from Cliente; 
 
select nome  

from Cliente 

order by nome asc;  

Resultado obtido: 

![image](https://github.com/user-attachments/assets/07f9360d-8a82-4604-8cb0-1b694f6e8a87)

4.	Implemente uma consulta para listar o nome de todas as editoras e os títulos de seus respectivos livros. A listagem deve ser mostrada em ordem decrescente pelo nome das editoras.

Código utilizado:

use livraria;

show tables; 

select * from Livro; 
 
select nome,titulo 

from Livro 

Left join Editora on Livro.idEditora = Editora.idEditora order by nome desc;

Resultado obtido: 

![image](https://github.com/user-attachments/assets/7ab85d69-e62c-4a3b-98f2-cb12b6de1864)

5.	Implemente uma consulta para listar o nome das editoras e a média de preço de seus respectivos livros. Para isso, utilize o comando group by.

Código utilizado: 

show databases;

use livraria; 

show tables; 
 
select nome as nome_editora, ROUND(avg(preco),2) as media_preco  

from Livro 

Left join Editora on Livro.idEditora = Editora.idEditora group by nome 

order by round(avg(preco),2); 

Resultado obtido: 

![image](https://github.com/user-attachments/assets/c307d58e-eaa6-4e97-8d49-9e3b0fdb3064)

6. Implemente uma consulta para listar o nome de todos os clientes e a quantidade de livros comprados pelos mesmos. Para isso, utilize o comando group by.

Código utilizado:

show databases; 

use livraria; 

show tables; 
 
select * from pedido; 

select * from itempedido;

select * from cliente; 

select nome as nome_cliente, sum(quantidade) as Quantidade_de_pedidos

from itempedido

left join pedido on itempedido.idPedido = pedido.idPedido

left join cliente on pedido.idCliente = cliente.idCliente

group by nome

order by sum(quantidade) desc;

Resultado obtido: 

![image](https://github.com/user-attachments/assets/f1c48333-844f-40ac-b770-fe67345da0f3)





