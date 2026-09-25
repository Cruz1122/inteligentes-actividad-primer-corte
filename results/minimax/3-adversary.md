# Pregunta final: ¿Por qué una decisión que parece buena de manera inmediata puede ser mala después de considerar la respuesta del adversario?

Porque el valor de una jugada no está en la casilla que uno ocupa, sino en lo que el otro puede hacer después. En el tres en raya del punto 1, X podía jugar en 6, 7 u 8. Jugar en 7 no pierde en el acto y hasta deja una hoja +1 si O se equivoca. MIN no se equivoca: elige el empate y esa rama vale 0. Jugar en 6 se ve como ocupar un hueco más, y MIN responde en 7 y completa la columna del medio. Esa rama vale -1.

La hoja que uno quiere, el +1 de la rama 7, no es la que elige el adversario. Minimax se queda con max(-1, 0, +1) y manda jugar en 8, donde X gana en el momento y O no alcanza a responder. Sin modelar a MIN, una jugada que “se ve bien ahora” puede ser la que le entrega la partida al otro.
