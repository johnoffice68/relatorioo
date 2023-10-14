# relatorioo


Uma empresa de vendas tem um banco de dados com informações sobre os seus produtos. Ela precisa criar um relatório que faça um levantamento diário da quantidade de produtos comprados por dia. Para ajudar a empresa, crie um procedure para agilizar esse processo.
<br>

DELIMITER //
CREATE PROCEDURE GerarRelatorioDiario()
BEGIN
    SELECT
        DATE(data_da_compra) AS Data,
        COUNT(*) AS QuantidadeDeProdutosComprados
        <br>
    FROM
        tabela_de_vendas
        <br>
    WHERE
        DATE(data_da_compra) = CURDATE()
        <br>
    GROUP BY
        DATE(data_da_compra);
        <br>
END//
DELIMITER ;
<br>
Essa procedure conta a quantidade de produtos comprados em um determinado dia (hoje, no caso, usando a função CURDATE()) e agrupa os resultados por data. 
