  

<!DOCTYPE html>

<html lang="es">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Screenplay</title>

<div id="screenplay">

    EXT/INT - Castillo tokushima - NOCHE - DOMINIO TOKUSHIMA

    1566年2月XX日 - Actualidad - (Prefectura de Tokushima)

    https://en.wikipedia.org/wiki/Tokushima_Domain

    https://es.wikipedia.org/wiki/Distrito_de_Katsuura#/media/Archivo:Tokushima-katsuura-district.svg

    El camino hacia el castillo Tokushima está más concurrido que de usual; los faroles se han iluminado en las últimas horas y hay un trasiego de carros, hombres y mujeres que caminan en dirección a la fortaleza del clan Hachisuka.

    Serán hasta tres días de celebración en la que el pueblo llano permanece en el terreno anexo al castillo tras la primera de las murallas, y los más pudientes y cercanos al daimyo Hachisuka disfrutarán de poder darse a conocer; cerrar negocios y aprovechar los placeres carnales para honrar al señor feudal por su benevolencia y sus efectos en el porvenir de la región.

    Y hoy hacían quince años desde su ascenso como líder y la celebración se esperaba aún mayor. Los comerciantes y propietarios exitosos y más reputados de la región llevan sus presentes en carretas y carros fuertemente vigilados, un intercambio que les permite acceder a los niveles más profundos de la fortaleza. Cuanto más exquisitos son los regalos más posibilidades hay de acercarse al señor feudal y su séquito mas privado y cuando eso pasa los negocios y el éxito están casi garantizados en su totalidad.

    Quizás hasta el mismísimo shogun, Tokuwaga Ietsuna, fuese a hacer aparición por lo que las expectativas estaban por las nubes y el castillo y los caminos que conducían a la fortaleza estaban más llenos de vida de lo usual y eso que la poca luz del Sol empezaba a diluirse por el horizonte.

    Pequeñas caravanas de mercaderes, comerciantes y viajeros recorrían en conjunto los caminos. No era inusual cruzarse con miembros de las familias vasallas del daimyo Hachisuka pero todos sabían que los asaltos, robos y crímenes se volvían mas probables cuanto más tardasen y, cuanto más tarde llegasen, aquellas ambiciones podían truncarse.

    Un pequeño grupo de carros habían salido desde Miyoshi, al oeste del dominio Tsukushima, a primera hora de la mañana hacía casi dos días atrás. Dos hombres de mediana edad hacían las de jinetes, subidos en corceles negroscuros, tras ellos habían dos carros, el primero llevaba una litera de madera cubierta tirada por dos caballos, la madera está grabada con delicadas formas pero apenas un par de hendiduras permiten ver el exterior desde dentro.

    Tres más tiraban del carro anterior que portaba hasta diez barriles llenos de la producción de sake personal y un par de ESCOLTAS contratados para la seguridad de aquella mercancía tan valiosa.

    Escolta

    Señor, ¿estais seguro de que os atenderá el daimyo? Hay más gente que nunca por estos caminos, Hachisuka-sama debe recibir más ofrendas de las que pueda apreciar.

    MINAMOTO MIYOSHI sonríe sin dejar de mirar al frente donde aquel castillo, iluminado por centenares de faroles destaca sobre el cielo cada vez mas oscuro.

    Minamoto MIYOSHI

    La mayoría de los presentes vendrán a agasajarlo, a intentar comprarle favores por otros. Puede que mi familia y mi negocio no estén a la altura de un daimyo pero los presentes no son lo mío. Son malos negocios.


</div>

</div>

<style>

body{font-family:'Courier New',Courier,monospace;background-color:#f4f4f4;margin:0;padding:20px;white-space:pre-line;text-align:justify}

.scene-heading{font-weight:700;text-transform:uppercase;margin-top:20px}.accion{margin:15px 0}.character{margin-left:150px;margin-top:15px;text-transform:uppercase;font-weight:700}.dialogue{margin-left:100px;margin-top:5px;margin-bottom:15px}.parenthetical{margin-left:120px;font-style:italic}.note{font-style:italic!important;color:#7a7a7a!important;margin:10px 0!important}</style>

  

<script>

    const screenplayDiv = document.getElementById('screenplay');

    const screenplayText = screenplayDiv.innerText;

    const lines = screenplayText.split('\n').map(line => line.trim()).filter(line => line !== '');

    screenplayDiv.innerHTML = ''; // Clear the existing text

    var esDialogo = false; //si anteriormente habló un personaje o hizo un parentesis

    var lastCharacter ='';

    lines.forEach(line => {

        let div = document.createElement('div');

        if (line.startsWith('INT.') || line.startsWith('EXT.') || line.startsWith('INT') || line.startsWith('EXT') || line.startsWith('INT/EXT')) {

            div.className = 'scene-heading';

        } else if (line.startsWith('(') && line.endsWith(')')) {

            div.className = 'parenthetical';

            esDialogo = true;

        } else if (line.length > 1 && !(line.endsWith('.') || line.endsWith('!') || line.endsWith('?')) || line.endsWith('??')) { // Ensure it's not just punctuation

            div.className = 'character';

            if (line!=lastCharacter) lastCharacter=line.toUpperCase;

            else line += " (CONT'D)"

            esDialogo = true;

        } else if ((line.includes('.') || line.includes('!') || line.includes('?')) && esDialogo) {

            div.className = 'dialogue';

            esDialogo = false;

        } else if (line.includes('A/N')){

            div.className = 'note'

        }

        else {

            div.className = 'accion';

        }

        div.textContent = line;

        screenplayDiv.appendChild(div);

    });

  

</script>