# PLSQL

CREATE [OR REPLACE] PROCEDURE inserePedido (

        numPedido IN NUMBER,
        dataPedido IN DATE,
        valorPedido IN NUMBER,
        clientePedido IN NUMBER) IS

BEGIN
  
  INSERT INTO pedido VALUES (numPedido, dataPedido, valorPedido, clientePedido);
  
  COMMIT WORK;
  
END inserePedido;

/

________________________________________________________________________________
________________________________________________________________________________


CREATE OR REPLACE PROCEDURE alteraPedido(

    numPedido IN NUMBER,
    novoValor IN NUMBER) IS
    
BEGIN

    UPDATE pedido
    SET valor = novoValor
    WHERE numero = numPedido;
    
    COMMIT WORK;

END alteraPedido;

/

________________________________________________________________________________
________________________________________________________________________________


CREATE OR REPLACE PROCEDURE deletaPedido(

        numPedido IN NUMBER) IS
        
        
BEGIN 
    
    DELETE FROM pedido WHERE numPedido = numero;
    
    COMMIT WORK;

END deletaPedido;

/


________________________________________________________________________________
________________________________________________________________________________

CREATE TABLE totalVendas (
    
    codCliente NUMBER(3) REFERENCES cliente (codigo),
    total NUMBER(12,2),
    PRIMARY KEY (codCliente) 

);


CREATE OR REPLACE PROCEDURE calculaTotalVendas(
    
    codCliente IN NUMBER ) IS
    
valorTotal NUMBER (12,2) := 0;

BEGIN 
    
    

END calculaTotalVendas;
/













