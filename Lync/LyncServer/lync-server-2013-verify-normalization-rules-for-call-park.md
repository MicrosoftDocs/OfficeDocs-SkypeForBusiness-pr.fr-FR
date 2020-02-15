---
title: 'Lync Server 2013 : vérifier les règles de normalisation pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ab8e6038fd17daed7f10f11023793b702dd7d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Vérifier les règles de normalisation pour le parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

Les orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez vos plans de numérotation pour vous assurer que les numéros d’orbite ne sont pas normalisés. Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure décrite dans [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a New Normalization Rule, de sorte que le **modèle de correspondance** identifie la plage d’orbites et le **modèle de traduction** est **$1**. Par exemple, si votre plage d’orbites de parcage d’appel est 7000 – 7999, le **modèle de correspondance** est **\\^ (7 d{3}) $** et le modèle de **traduction** est **$1**.

<div>


> [!IMPORTANT]  
> Assurez-vous que la règle de normalisation par défaut de vos plans de numérotation ne contient pas <STRONG>^ (\d *)</STRONG>. Dans le cas contraire, votre règle de normalisation de parcage d’appel ne s’exécutera jamais.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

