---
title: 'Lync Server 2013 : définition des règles de normalisation'
description: 'Lync Server 2013 : définition des règles de normalisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a123e17b1d3256781ff34e4cade2b344ba8fe14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542040"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a>Définition de règles de normalisation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-22_

Les règles de normalisation Lync Server 2013 utilisent des expressions régulières .NET Framework pour convertir les numéros de téléphone composés au format E. 164 ; en d’autres termes, les règles de normalisation prennent le numéro de téléphone composé par un utilisateur et convertissent ce nombre au format utilisé en interne par Lync Server. Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.

Pour plus d’informations sur les règles de normalisation, voir [Dial plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.

Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « .NET Framework regular expressions » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

Vous pouvez utiliser l’une des méthodes suivantes pour définir ou modifier une règle de normalisation :

  - Utilisez l’outil de **création d’une règle de normalisation** pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez le panneau de configuration Lync Server générer le modèle de correspondance et la règle de traduction correspondants pour vous.

  - Écrivez les expressions régulières manuellement pour définir le modèle correspondant et la règle de traduction.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Création ou modification d’une règle de normalisation à l’aide de la création d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

