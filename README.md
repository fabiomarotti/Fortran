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
    real,       PARAMETER :: pi = 3.1415927    ! constantes
    character,  PARAMETER :: kg = "kilo grama" 
    
    integer(kind=2)
    integer(kind=4)
    integer
    integer(kind=8)
    integer(kind=16)
    
    real                :: salario 
    double precision    :: media 
    
    complex             :: num_complexo  
    logical             :: logico 
    character(len = 80) :: texto
    
    texto = "abcdef"
    print*, texto(1:3) ! escreve abc
    
    ! função kind(variavel)
    ! informa o tipo da variavel
    
    ! função huge(variavel)
    ! mostrar maior número mantido pela variavel
    
    ! função trim(texto)
    ! exclui espaço em branco no meio do texto
~~~

#### Livrarias
~~~Fortran
    RANDLIB, random number and statistical distribution generators
    BLAS
    EISPACK
    GAMS–NIST Guide to Available Math Software
    Some statistical and other routines from NIST
    LAPACK
    LINPACK
    MINPACK
    MUDPACK
    NCAR Mathematical Library
    The Netlib collection of mathematical software, papers, and databases.
    ODEPACK
    ODERPACK, a set of routines for ranking and ordering.
    Expokit for computing matrix exponentials
    SLATEC
    SPECFUN
    STARPAC
    StatLib statistical library
    TOMS
    Sorting and merging strings
~~~

#### Funções Intrinsicas

| Função    | Descrição do retorno :: (radianos)    |
|---        |---            |
|sin(x)     | seno                                  |
|sinh(x)    |seno hiperbolico                       |
|asin(x)    |arco seno: intervalo (-pi/2 , pi/2)    |
|cos(x)     |cosseno                                |
|cosh(x)    |cosseno hiperbolico                    |
|acos(x)    |arco cosseno: intervalo (0 ,  pi )     |
|tan(x)     |tangente                               |
|tanh(x)    |tangente hiperbolica                   |
|atan(x)    |arco tangente: intervalo (-pi/2 , pi/2)|
|atan2(x)   |arco tangente: intervalo (-pi , pi)    |
|log(x)     |logaritmo Natural (base e)             |
|log10(x)   |logaritmo         (base 10)            |
|exp()      |retorna o expoente do número           |


