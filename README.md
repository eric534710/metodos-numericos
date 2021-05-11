# metodos-numericos

function [p, v ]=Plagrange(x0, y0, u)
syms x;
 % salida inicializado en cero 
 %donde x=n:m  and y=n:m
p(x) =0*x;
N= length(x0)-1;
for k=0:N
    %  producto numerador y denomiador
    pNum=1;
    pDen=1;
    for j = 0:N
    if j~=k
   
        pNum=pNum*(x-x0(j+1));
        pDen=pDen*(x0(k+1)-x0(j+1));
    end
        
    end
    L=pNum/pDen;
% calculamos polinomio en p dada la formula
p=p + y0(k+1)*L;
end
%muestra solo hasta 6 digitos
digits(6)
%interpolacion valor v
%ejecutar como Plagrange(x0, y0, u)
v=p(u);

end
