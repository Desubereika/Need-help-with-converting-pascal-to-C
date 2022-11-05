PROGRAM Calcul_Sinus;
VAR x, Rad, pi, Sinus : REAL;
    Sign : SHORTINT;
BEGIN
WRITELN('Calcul du sinus d''un angle.');
WRITE('Introduisez l''angle (en radians):');
READLN(x);
pi:=3.1416;
Rad := x;
Sign := +1;
IF Rad>0 THEN Rad := Rad - 2*pi * TRUNC(Rad / (2*pi))
ELSE Rad := Rad + 2*pi * TRUNC(-Rad / (2*pi)) + (2*pi);
IF Rad > pi THEN BEGIN
                 Rad := Rad - pi;
                 Sign :=-1
                 END;
IF Rad > pi/2 THEN Rad :=pi - Rad;
IF Rad > pi/4 THEN BEGIN
                   Rad :=pi/2 - Rad;
                   Sinus :=1 - Rad*Rad/2 + Rad*Rad*Rad*Rad/24
                   END
ELSE Sinus :=Rad - Rad*Rad*Rad/6 + Rad*Rad*Rad*Rad*Rad/120;
Sinus := Sinus * Sign;
WRITELN('sin(',x,')=',Sinus)
END.
