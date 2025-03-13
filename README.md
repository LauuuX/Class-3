# Transformada inversa (Método resumido)
## Fracciones parciales método resumido 
> 🔑 Aprovechando que para la descomposición en fracciones parciales se deben factorizar las ríces del polinomio del numerador, se puede saber para que valores s s s eliminan algunos términos; lo cuál reduce el sistema de ecuaciones que debe ser solucionado.
## 1. Caso 1: Raíces reales diferentes 

$$F(s) = \frac{A(s)}{B(s)} = \frac{a_1}{s + p_1} + \frac{a_2}{s + p_2} + \dots + \frac{a_n}{s + p_n}$$

- Sabiendo que $$a_k(1,2,3..)$$ son constantes, $$a_k$$ puede hallarse multiplicando ambos lados de la iguladad por $$(s + p_k)$$ y haciendo $$(s = -p_k)$$, de lo cual se obtiene:

- La transformada inversa de Laplace para funciones racionales con denominadores que tienen raíces reales y diferentes se calcula mediante expansión en fracciones parciales.

- Cuando tenemos una función racional $F(s) = \frac{A(s)}{B(s)}$ donde $B(s)$ tiene raíces reales y distintas $-p_1, -p_2, ..., -p_n$, la expansión en fracciones parciales es:

$$F(s) = \frac{A(s)}{B(s)} = \frac{a_1}{s + p_1} + \frac{a_2}{s + p_2} + ... + \frac{a_n}{s + p_n}$$

- *Cálculo de los coeficientes* 

- Los coeficientes $a_k$ se calculan usando el método del residuo:

$$a_k = \left[(s + p_k)\frac{A(s)}{B(s)}\right]_{s=-p_k}$$

- Esto funciona porque al evaluar la expresión en $s = -p_k$, todas las demás fracciones se cancelan, quedando solo $a_k$.

- Desarrollando el lado derecho:

$$\left[\frac{a_1}{s + p_1}(s + p_k) + \frac{a_2}{s + p_2}(s + p_k) + ... + \frac{a_k}{s + p_k}(s + p_k) + ... + \frac{a_n}{s + p_n}(s + p_k)\right]_{s=-p_k} = a_k$$

- Cuando $s = -p_k$, el término $\frac{a_k}{s + p_k}(s + p_k)$ se convierte simplemente en $a_k$, mientras que todos los demás términos se anulan porque $(s + p_k)$ se hace cero en el numerador.

- Aplicación de la transformada inversa

- Una vez obtenidos los coeficientes, la transformada inversa se calcula usando la propiedad:

$$\mathcal{L}^{-1}\{\frac{a_k}{s + p_k}\} = a_k e^{-p_k t}$$

- Por lo tanto, la transformada inversa completa será:

$$\mathcal{L}^{-1}\{F(s)\} = a_1e^{-p_1t} + a_2e^{-p_2t} + \ldots + a_ne^{-p_nt}$$

- Esta fórmula proporciona la solución en el dominio del tiempo de manera directa, siendo especialmente útil para resolver ecuaciones diferenciales lineales con coeficientes constantes.

## - 💡 *Ejemplo 1:*

$$F(s) = \frac{s+3}{(s+1)(s+2)}$$

## Paso 1: Expandir en fracciones parciales

- Expresamos $F(s)$ como:

$$F(s) = \frac{A}{s+1} + \frac{B}{s+2}$$

## Paso 2: Calcular los coeficientes A y B

- Para calcular A:

$$A = (s+1)F(s)|s=-1 = (s+1)(s+3)/((s+1)(s+2))|s=-1 = (s+3)/(s+2)|s=-1 = (-1+3)/(-1+2) = 2/1 = 2$$

- Para calcular B:

$$B = (s+2)F(s)|s=-2 = (s+2)(s+3)/((s+1)(s+2))|s=-2 = (s+3)/(s+1)|s=-2 = (-2+3)/(-2+1) = 1/(-1) = -1$$

- Por lo tanto:

$$F(s) = \frac{2}{s+1} - \frac{1}{s+2}$$

## Paso 3: Aplicar la transformada inversa término a término

 Usando la propiedad $$L^{-1}\{\frac{1}{s+p}\} = e^{-pt}$$:

$$L^{-1}\{F(s)\} = L^{-1}\{\frac{2}{s+1}\} - L^{-1}\{\frac{1}{s+2}\}$$

$$L^{-1}\{F(s)\} = 2e^{-t} - e^{-2t}$$

- Por lo tanto, la transformada inversa de Laplace de $F(s) = \frac{s+3}{(s+1)(s+2)}$ es:

$$f(t) = 2e^{-t} - e^{-2t}$$

## 2. Caso 2: Raíces reales iguales 
- ## 💡 *Ejemplo 2:*

$$F(s) = \frac{s^2 + 2s + 3}{(s + 1)^3}$$

- ## Cálculo de coeficiente
$$D_3 = [(s + 1)^3 \frac{A(s)}{B(s)}]_{s=-1} = (s^2 + 2s + 3)_{s=-1} = 2$$

$$D_2 = [\frac{d}{ds}[(s + 1)^3 \frac{A(s)}{B(s)}]]_{s=-1} = [\frac{d}{ds}(s^2 + 2s + 3)]_{s=-1} = (2s + 2)_{s=-1} = 0$$

$$D_1 = \frac{1}{2!}[\frac{d^2}{ds^2}[(s + 1)^3\frac{A(s)}{B(s)}]]_{s=-1} = \frac{1}{2!}[\frac{d^2}{ds^2}(s^2 + 2s + 3)]_{s=-1} = \frac{1}{2}(2) = 1$$

- ## Fórmula para transformada inversa
$$t^n e^{at},\; n=1,2,3,\ldots \Rightarrow \frac{n!}{(s-a)^{n+1}}$$

- ## Solución final
$$f(t) = \mathcal{L}^{-1}[F(s)]$$
$$= \mathcal{L}^{-1}\left[\frac{2}{(s+1)^3}\right] + \mathcal{L}^{-1}\left[\frac{0}{(s+1)^2}\right] + \mathcal{L}^{-1}\left[\frac{1}{s+1}\right]$$
$$= t^2e^{-t} + 0 + e^{-t}$$
$$= (t^2 + 1)e^{-t} \quad (t \geq 0)$$

## 3. Caso 3: Raíces complejas conjugadas
- ## 💡 *Ejemplo 3:*
  ## Caso 3: Raíces complejas conjugadas

- ### Función de transferencia

$$F(s) = \frac{2s + 12}{s^2 + 2s + 5}$$

- Si las raíces son complejas:

$$s^2 + 2s + 5 = (s + 1 + j2)(s + 1 - j2)$$

- Sabiendo que este tipo de raíces resulta en la suma de una función seno amortiguada con una coseno amortiguado:

- De tabla de transformadas:

$$\mathcal{L}[e^{-\alpha t} \sin \omega t] = \frac{\omega}{(s + \alpha)^2 + \omega^2}$$

$$\mathcal{L}[e^{-\alpha t} \cos \omega t] = \frac{s + \alpha}{(s + \alpha)^2 + \omega^2}$$

- ### Completando el cuadrado

$$F(s) = \frac{2s + 12}{s^2 + 2s + 5} = \frac{2s + 12}{s^2 + 2s + 5 - 4 + 4}$$

$$F(s) = \frac{2s + 12}{(s + 1)^2 + 2^2}$$

- Modificando numerador para suma de seno y coseno amortiguados:

$$F(s) = \frac{10 + 2(s + 1)}{(s + 1)^2 + 2^2} = 5 \frac{2}{(s + 1)^2 + 2^2} + 2 \frac{s + 1}{(s + 1)^2 + 2^2}$$

- Transformada inversa:

$$f(t) = \mathcal{L}^{-1}[F(s)]$$

$$f(t) = 5 \mathcal{L}^{-1} \left[ \frac{2}{(s + 1)^2 + 2^2} \right] + 2 \mathcal{L}^{-1} \left[ \frac{s + 1}{(s + 1)^2 + 2^2} \right]$$

$$f(t) = 5e^{-t} \sin 2t + 2e^{-t} \cos 2t \quad \text{para} \quad t \geq 0$$

# 1. Transformada de LaPlace en Matblab 
## 1.1 Transformada de Laplace (Directa)

## Transforme al dominio $$s: \( 8sen(4t) - 5\cos(4t) \)$$

```matlab
% Para obtener la transformada de Laplace Y(s), el comando syms genera las variables t y s
% La notación con minúscula supone una función definida en t
syms t s
y = 8*sin(4*t) - 5*cos(4*t);

% La notación con mayúscula indica una función transformada
Y = laplace(y)
```

- Salida:

```matlab
Y = (32/(s^2 + 16)) - ((5*s)/(s^2 + 16))
```

- Por lo tanto:

$$\[ \mathcal{L}\{8sen(4t) - 5\cos(4t)\} = \frac{32}{s^2 + 16} - \frac{5s}{s^2 + 16} \]$$

---

## 1.2 Transformada de Laplace (Inversa)

## Obtenga la transformada inversa de $$\( Y(s) = \frac{6s - 4}{s^2 + 4s + 20} \)$$

```matlab
% La transformada inversa de Laplace se obtiene con el comando syms
% que genera variables s y t para pasar del dominio s al t
syms s t
Y = (6*s - 4)/(s^2 + 4*s + 20);

y = ilaplace(Y)
```

 Salida:

```matlab
y = 6*exp(-2*t) * (cos(4*t) - (2*sin(4*t))/3)
```

- Por lo tanto:

$$\mathcal{L}^{-1} \bigg( \frac{6s - 4}{s^2 + 4s + 20} \bigg) = 6e^{-2t} \cos(4t) - 4e^{-2t} sen(4t)$$

# 2. Solución de ecuaciones diferenciales
## Metodología de solución 
- Aplicar transformada de LaPlace a toda la ecuación (término a término), de tal manera que se obtenga una ecuación algebráica en el dominio de s.
- Despejar la variable que representa la salida de la ecuación.
- Aplicar transformada inversa de LaPlace a la expresión obtenida para obtener la solución en el dominio del tiempo
  
## - 💡 *Ejemplo 1:*

- Dada la ecuación diferencial:

$$ \ddot{x} + 3\dot{x} + 2x = 0, \quad x(0) = a, \quad \dot{x}(0) = b $$

### Aplicando la Transformada de Laplace

$$ [s^2X(s) - sx(0) - \dot{x}(0)] + 3[sX(s) - x(0)] + 2X(s) = 0 $$

- Sustituyendo condiciones iniciales:

$$ [s^2X(s) - as - b] + 3[sX(s) - a] + 2X(s) = 0 $$

- Despejamos \(X(s)\):

$$ X(s) = \frac{as + b + 3a}{s^2 + 3s + 2} = \frac{as + b + 3a}{(s + 1)(s + 2)} $$

- Factorizando:

$$ X(s) = \frac{2a + b}{s + 1} - \frac{a + b}{s + 2} $$

### Aplicando la Transformada Inversa

$$ x(t) = \mathcal{L}^{-1} [X(s)] = \mathcal{L}^{-1} \left[ \frac{2a + b}{s + 1} \right] - \mathcal{L}^{-1} \left[ \frac{a + b}{s + 2} \right] $$

- Finalmente:

$$ x(t) = (2a + b)e^{-t} - (a + b)e^{-2t}, \quad t \geq 0 $$


## - 💡 *Ejemplo 2:*

$$(s^2 X(s) - sx(0) - \dot{x}(0)) + 2(s X(s) - x(0)) + 5X(s) = \frac{3}{s}$$

- Sustituyendo las condiciones iniciales:

$$(s^2 + 2s + 5)X(s) = \frac{3}{s}$$

$$X(s) = \frac{3}{s(s^2 + 2s + 5)}$$

### 2. Descomposición en fracciones parciales

- Factorizamos el denominador cuadrático:

$$s^2 + 2s + 5 = (s+1)^2 + 4$$

- Descomponemos en fracciones parciales:

$$\frac{3}{s(s^2 + 2s + 5)} = \frac{A}{s} + \frac{Bs + C}{s^2 + 2s + 5}$$

- Resolviendo para A, B y C:

$$A = \frac{3}{5}, \quad B = -\frac{3}{5}, \quad C = -\frac{6}{5}$$

$$X(s) = \frac{3/5}{s} + \frac{(-3/5)s - 6/5}{s^2 + 2s + 5}$$

### 3. Aplicamos la Transformada Inversa de Laplace

$$x(t) = \frac{3}{5} - \frac{3}{5} e^{-t} \cos(2t) - \frac{3}{5} e^{-t} \sin(2t)$$

## **Resultado Final**

$$\mathbf{x(t) = \frac{3}{5} - \frac{3}{5} e^{-t} \cos(2t) - \frac{3}{5} e^{-t} \sin(2t)}$$

# 3. Solución de la ecuación diferencial

$$\frac{dy}{dt} = 5 - 2y$$

- Con condición inicial:

$$y(0) = 0$$

## Solución Analítica

- La solución de la ecuación diferencial es:

$$y(t) = \frac{5}{2} - \frac{1}{2} e^{-2t}$$


### Código en MATLAB

```matlab
syms y(t)
% Definir la ecuación diferencial
eqn = diff(y, t) + 2*y == 5;
% Definir las condiciones iniciales
cond1 = y(0) == 0;
% Resolver la ecuación diferencial
sol = dsolve(eqn, cond1);
% Mostrar la solución
disp(sol);
```
![Solución Analítica](https://github.com/user-attachments/assets/7cadc408-846e-47c3-8cdb-787deb70e0a9)

Figura 2: Solucipon analítica
## Solución Numérica en MATLAB

```matlab
tspan = [0 10];
cond1 = 0;
[t, y] = ode45(@(t, y) 5 - (2*y), tspan, cond1);

% Graficar solución
plot(t, y, 'b', 'LineWidth', 2);
grid on;
xlabel('Tiempo (t)');
ylabel('Variable y(t)');
title('Solución ecuación dy/dt=5-2y');
```
![Simulación en Simulink](https://github.com/user-attachments/assets/7d01243b-53f1-4c99-a9c3-dbadb9f11ed6)

Figura 1: Simulik

## Simulación en Simulink

- Se ha implementado la ecuación diferencial en Simulink utilizando integradores y bloques matemáticos.
  
![Solución Numérica](https://github.com/user-attachments/assets/cc76969a-7e37-4de0-a7aa-2e632bb14e48)

Figura 3: Solución numérica
## Ejecicios extras 
### 💡 *Ejemplo 1:*
#### Raíces Complejas Conjugadas

$$ s^2 + 2s + 8 = (s + 1)^2 + 2^2 $$

$$ 2s + 12 = -10 + 2(s + 1) $$

$$ F(s) = \frac{-10 + 2(s+1)}{(s+1)^2 + 2^2} $$

-  Separación en términos reconocibles

$$ F(s) = \frac{-10}{(s+1)^2 + 2^2} + \frac{2(s+1)}{(s+1)^2 + 2^2} $$

- Se usa las transformadas inversas conocidas:

$$\( \mathcal{L}^{-1} \left[ \frac{b}{(s+a)^2 + b^2} \right] = e^{-at} \sin(bt) \)$$
$$\( \mathcal{L}^{-1} \left[ \frac{s+a}{(s+a)^2 + b^2} \right] = e^{-at} \cos(bt) \)$$

- Aplicamos a nuestra expresión:

$$ f(t) = -10 e^{-t} \sin(2t) + 2 e^{-t} \cos(2t) $$


### 💡 *Ejemplo 2:*
#### Raíces reales y repetidas 

$$f(s) = \frac{s^2 + 3s + 5}{(s+3)^3} = \frac{b_2}{(s+3)^3} + \frac{b_1}{(s+3)^2} + \frac{b_0}{(s+3)}$$

$$f(s) = \frac{s^2 + 3s + 5}{(s+3)^3} \cdot (s+3)^3 |_{s=-3}$$

$$f(s) = s^2 + 3s + 5|_{s=-3}$$

$$f(-3) = (-3)^2 + 3(-3) + 5$$

$$f(-3) = 9 - 9 + 5 = 5$$

$$f(-3) = 5 - b_3$$

- La segunda derivada para hallar $$b_2$$

$$f(-3) = (2s + 3)$$

$$f(-3) = (2(-3) + 3)$$

$$f(-3) = -3 - b_2$$

- Para hallar $$b_1$$

$$\frac{d^2}{ds^2} (s^2 + 3s + 5)$$

- Sustituyendo en la expresión de $$\( b_1\)$$:

$$b_1 = \frac{1}{2!} \cdot (2) = \frac{1}{2} \cdot 2 = 1$$

- Por lo tanto,
  
$$b_1 = 1$$

$$5 \mathcal{L}^{-1} \left[ \frac{1}{(s+3)^3} \right]$$
$$- 3 \mathcal{L}^{-1} \left[ \frac{1}{(s+3)^2} \right]$$
$$+ \mathcal{L}^{-1} \left[ \frac{1}{(s+3)} \right]$$

- Usando las fórmulas de transformada inversa:

$$\mathcal{L}^{-1} \left[ \frac{1}{(s+a)^n} \right] = \frac{t^{n-1}}{(n-1)!} e^{-at}$$

$$\mathcal{L}^{-1} \left[ \frac{1}{s+a} \right] = e^{-at}$$

- Obtenemos:

$$5 \frac{t^2}{2!} e^{-t} - 3 t e^{-3t} + e^{-3t}$$

