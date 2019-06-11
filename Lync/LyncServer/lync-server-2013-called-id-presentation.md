---
title: 'Lync Server 2013: appelé présentation ID'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bd84e60118697c94aba6c6088de68fc37d34c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Appelée présentation ID dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Avec Lync Server 2010, le numéro de téléphone de la personne appelé (c’est-à-dire, le numéro de téléphone appelé) peut être converti à partir du format E. 164 vers le format de numérotation local requis par le Trunk pair (c’est-à-dire, la passerelle associée, le PBX (PBX) ou le Trunk SIP). À cet effet, vous devez définir une ou plusieurs règles de traduction pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.

<div>


> [!IMPORTANT]  
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de Trunk vocale d’entreprise est conçue pour être utilisée comme <EM>alternative</EM> à la configuration de règles de traduction sur l’homologue de Trunk. N’associez pas de règles de traduction à une configuration de Trunk vocale d’entreprise si vous avez configuré des règles de traduction sur le Trunk homologue, car les deux règles peuvent entrer en conflit.



</div>

Pour créer ou modifier une règle de traduction, vous pouvez utiliser l’une des méthodes suivantes:

  - Utilisez l’outil **créer une règle de traduction** pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez le panneau de configuration de Lync Server générer le modèle correspondant et la règle de traduction correspondants.

  - Rédigez manuellement des expressions régulières pour définir les modèles correspondants et les règles de traduction.

<div>


> [!NOTE]  
> Pour plus d’informations sur la façon d’écrire des expressions régulières, voir «expressions <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>régulières .NET Framework» à l’adresse.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Créer ou modifier une règle de traduction à l’aide de l’outil créer une règle de traduction dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Créer ou modifier une règle de traduction manuellement dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Présentation de l’identification de l’appelant dans Lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

