---
title: 'Lync Server 2013 : utilisation des options de ligne de commande du programme d’installation'
description: 'Lync Server 2013 : utilisation des options de ligne de commande du programme d’installation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15c3490ead090766462ce83cb13ffe62355032cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580240"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Utilisation des options de ligne de commande du programme d’installation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office. Au lieu d’utiliser les options de ligne de commande du programme d’installation, vous utiliserez généralement l’outil de personnalisation Office et le fichier Config.xml pour la personnalisation des composants et de la configuration du produit.

La ligne de commande Office Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.

### <a name="office-setup-command-line-options"></a>Options d’installation d’Office Command-Line

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option de Command-Line de configuration</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Exécute l’Outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [chemin]</p></td>
<td><p>Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.</p></td>
</tr>
<tr class="odd">
<td><p>/config [chemin]</p></td>
<td><p>Spécifie le fichier Config.xml que le programme d’installation utilise au cours de l’installation. Utilisez l’option/config pour spécifier le fichier de Config.xml que vous avez personnalisé pour les installations de Lync 2013, par exemple : <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/Modify Lync</p></td>
<td><p>Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante. Par exemple, vous pouvez utiliser l’option/Modify pour ajouter ou supprimer des fonctionnalités Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/Repair Lync</p></td>
<td><p>Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Lync.</p></td>
</tr>
<tr class="even">
<td><p>/Uninstall Lync</p></td>
<td><p>Exécute le programme d’installation pour supprimer Lync de l’ordinateur de l’utilisateur.</p></td>
</tr>
</tbody>
</table>


Pour plus d’informations sur l’utilisation des options de ligne de commande du programme d’installation, voir <https://go.microsoft.com/fwlink/p/?linkid=267515> .

</div>

<span> </span>

</div>

</div>

</div>

