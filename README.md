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

#### Arrays (DIMENSION)
~~~Fortran
    integer,    dimension (3)        :: idades
    real,       dimension (4)        :: medias
    integer,    dimension (3,3)      :: matriz_idades   ! matriz 3x3
    real,       dimension (2:6)      :: numbers
    integer,    dimension (-3:2,0:4) :: matrix  

    ! Atribuição de modo curto
    medias = (/ 1.5, 28, 3.14/)
~~~

* Funções de Informações das Matrizes
~~~Fortran
   real, dimension(3,2) :: a 
   a = reshape( (/5,9,6,10,8,12/), (/3,2/) ) 
   
   Print *, lbound(a, dim = 1)  ! retorna o limite superior da dimensão, sem dim: retorna vetor inteiro
   Print *, ubound(a, dim = 1)  ! retorna o limite inferior da dimensão (pode ser negativo)
   Print *, shape(a)            ! dimensão da matriz
   Print *, size(a,dim = 1)     ! número elementos da determinada dimensão
~~~  
* Funções de Manipulações das Matrizes
~~~Fortran
   real, dimension(1:6) :: a = (/ 21.0, 22.0, 23.0, 24.0, 25.0, 26.0 /)
   real, dimension(1:6) :: x, y
   write(*,10) a
   
   ! soma/subtrai o valor de shift em todos os campos
   x = cshift ( a, shift = 2)
   write(*,10) x
   y = cshift (a, shift = -2)
   write(*,10) y
   
   ! desloca todos os elementos (+: esquerda) (-: direita)
   x = eoshift ( a, shift = 2)
   write(*,10) x   
   y = eoshift ( a, shift = -2)
   write(*,10) y
   
   10 format(1x,6f6.1)
   
   
~~~ 

* Funçoes de Localização para Arrays
~~~Fortran
   real, dimension(1:6) :: a = (/ 21.0, 12.0,33.0, 24.0, 15.0, 16.0 /)
   Print *, maxloc(a)       ! retorna a posição do maximo local :3
   Print *, minloc(a)       ! retorna a posição do mínimo local :2
~~~

#### Tipos (Estrutura, Classe)
~~~Fortran
! Declaração
type    Pessoa
    character(len=50)   ::  nome
    integer             ::  idade
end type Pessoa

! Instância do Tipo/Estrutura/Classe
type(Pessoa) :: p01
type(Pessoa) :: p02
type(PEssoa), dimension(2) :: listaPessoas

! manipulando
p01%nome    = "Fulano"
p01%idade   = 28
p02%nome    = "Ciclano"
p02%idade   = 38

listaPessoas(1)%nome    = "Fulano"
listaPessoas(1)%idade   = 28
listaPessoas(2)%nome    = "Ciclano"
listaPessoas(2)%idade   = 38
~~~
#### Operadores

Operador Aritmético
|Operador   |Equivalente    | 
|---        |---            |
| +         | Soma          |
| -         | Subtração     |
| *         | Multiplicação |
| /         | Divisão       |
| **        | Potencia      |

Operador Relacional
|Operador   |Equivalente    | Descrição     |
|---        |---            |---            |
| ==        | .EQ.          | Igualdade     |
| /=        | .NE.          | Diferente     |
| >         | .GT.          | Maior que     |
| <         | .IT.          | Menor que     |
| >=        | .GE.          | Maior igual   |
| <=        | .LE.          | Menor igual   |

Operador Lógico
|Operador   |Descrição      | 
|---        |---            |
| .AND.     |  E            |
| .OR.      | OU            |
| .NOT.     | Não           |
| .EQV.     | Equivalência entre dois operadores lógicos     |
| .NEQV.    | Não Equivalência entre dois operadores lógicos |

Precedencia dos Operadores
|Categoria                      |Operador          | Associativa              |
|---                            |---                |---                      |
| Não lógico e sinal negativo   | .NOT. , (-)       | Esquerda para direita   |
| Expoente                      | **                | Esquerda para direita   |
| Multiplicação, Divisão        | * , /             | Esquerda para direita   |
| Adição, Subtração             | + , -             | Esquerda para direita   |
| Relacional                    | < , <= , > , >=   | Esquerda para direita   |
| Igualdade, Desigualdade       | == , /=           | Esquerda para direita   |
| E lógico                      | .AND.             | Esquerda para direita   |
| OU lógico                     | .OR.              | Esquerda para direita   |
| Atribuição                    | =                 | Direita para esquerda   |


#### Entrada/Saída (I/O)
~~~Fortran
read(*,*) x
write(*,*) "Ola Mundo", x
print *, "Ola Mundo", x
~~~

~~~Fortran
read    fmt, variavel
print   fmt, variavel
write   fmt, variavel
~~~

|Descritor  |Descrição          |Exemplo                |
|---        |---                |---                    |
|i          |inteiros           | print "(3i5)", x      |
|f          |real               | print "(f12.3)", x    |
|e          |expoencial         | print "(e10.3)" ,123456.0 gives ‘0.123e+06’ |
|es         |notação cientifica | print "(es10.3)",123456.0 gives ‘1.235e+05’ |
|a          |caracteres         | print "(a10)", str        |
|x          |criar espaço (5x)  | print "(  5x, a10)",  str |
| /         |linha em branco    | print "(/,5x, a10)", str  |

~~~Fortran
 print '( / , 3x , "n = " , i6 , 3x , "d = " , f7.4 )', n, d
! pula linha, 3 espaços, "texto", inteiros, 3 espaços, "texto", real
~~~

Formatação

~~~Fortran
        print 100
100     format (7x,'Nome:', 7x, 'Idade:', 1x, 'Nascimento:')

        print 200, nome,   idade,     nascimento
200     format(1x,    a, 2x,  i3, 2x,       f5.2)  

~~~


#### Estruturas de Decisão
* IF - THEN - ELSE - END IF
~~~Fortran
! Estrtrutura IF - THEN - ELSE - END IF
if (x > 2) then
       ! fazer01
    else if(x > 8) then
       ! fazer02
    else if (x > 10) then
       ! fazer03
    end if

! com nome    
gr: if( x>2 ) then
       !fazer01
    enf if gr
~~~

* SELECT CASE
~~~Fortran
select case(nota)
    case(10)
    ! faça para 10
    
    case(5 : 9)
    ! faça para entre 5 e 9
    
    case(:4)
    ! faça para menor que 4
    
    case default
    ! faça caso contrario
end select
~~~

#### Estrutura de Repetição
~~~Fortran
    ! DO simples
    do i=1, 10
        ! faça
    end do
    
    ! DO WHILE
    do while( x>2 )
        ! faça
    end do
    
    ! DO rotulado
    i_repetir: do i=1, 10
        j_repetir: do j=1, 10
            k_repetir: do k=1, 10
            
                ! fazer print*, "(i, j, k): ", i, j, k
               
             end do k_repetir
         end do j_repetir
     end do i_repetir
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
|exp(x)      |retorna o expoente do número          |

continuar em: https://www.tutorialspoint.com/fortran/fortran_intrinsic_functions.htm


