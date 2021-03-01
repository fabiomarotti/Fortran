# Fortran
Repositório com estudos realizados sobre a linguagem FORTRAN.

## Anotações


#### Compilador: Force 2.0.9 + GNU Fortran (GFortran) 
* [link para download](http://force.lepsch.com/p/download.html)

#### Links 
- [USP - Projeto MAC Multimídia](https://www.ime.usp.br/~macmulti/exercicios/inteiros/)
- [Tutorials Point](https://www.tutorialspoint.com/fortran/fortran_loops.htm)
- [Francisco Carlos Lavarda](http://wwwp.fc.unesp.br/~lavarda/fc1/apo/fort_09.htm)
- [Hans Rogério](https://github.com/zrhans/Fortran)

# Sintaxe
#### Estrutura básica
~~~fortran
! ----------------------- Programa Principal
program nome_programa
    implicit none 
    
    ! declaração de tipos e variáveis
    integer x, y
    
    ! instruções executáveis
    call somar(x,y)
    
PAUSE    
end program nome_programa

! ----------------------- Declaração de funções e procedimentos
function somar(a, b)
    implicit none
    somar = a + b
end function somar

subrotine dizer_bomDia( n )
    implicit none
    write(*,*) "Bom dia ", n , " !!! "
end subrotine dizer_bomDia
~~~

#### Variáveis
~~~Fortran
    integer(kind=2)
    integer(kind=4)
    integer
    integer(kind=8)
    integer(kind=16)
    
    
    real                :: salario 
    double precision    :: me 
    complex             :: num_complexo  
    logical             :: logico 
    character(len = 80) :: texto
    
    !função kind(variavel)
    !informa o tipo da variavel
    
    texto = "abcdef"
    print*, texto(1:3) ! escreve abc
    
    !função trim(texto)
    !exclui espaço em branco no meio do texto
~~~


