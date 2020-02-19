---
title: 'Lync Server 2013 : présentation de l’ID appelée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b4ad6f728f01f0cf9ef1aac6ed57ad22c7ff345
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Présentation de l’ID appelée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Avec Lync Server 2010, le numéro de téléphone de la partie appelée (c’est-à-dire, le numéro de téléphone appelé) peut être converti à partir du format E. 164 vers le format de numérotation local requis par l’homologue de jonction (c’est-à-dire, la passerelle associée, le PBX (Private Branch Exchange) ou la jonction SIP). Pour ce faire, vous devez définir une ou plusieurs règles de traduction pour traduire l’URI de demande avant de l’acheminer vers l’homologue de jonction.

<div>


> [!IMPORTANT]  
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de jonction Voix Entreprise peut servir d’<EM>alternative</EM> à la définition de règles de traduction sur l’homologue de jonction. N’associez pas de règles de traduction avec une configuration de jonction Voix Entreprise si vous avez configuré les règles de traduction sur le pair de jonction, car les deux règles risqueraient de provoquer un conflit.



</div>

Vous pouvez employer l’une des méthodes suivantes pour créer ou modifier une règle de traduction :

  - Utilisez l’outil **créer une règle de traduction** pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez le panneau de configuration Lync Server générer le modèle de correspondance et la règle de traduction correspondants pour vous.

  - Écrivez les expressions régulières manuellement pour définir le modèle correspondant et la règle de traduction.

<div>


> [!NOTE]  
> Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « .NET <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>Framework regular expressions » à l’adresse.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Création ou modification d’une règle de conversion à l’aide de l’outil créer une règle de traduction dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Création ou modification manuelle d’une règle de traduction dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Présentation de l’ID de l’appelant dans Lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

