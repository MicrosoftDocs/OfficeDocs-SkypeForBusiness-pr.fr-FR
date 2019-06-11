---
title: 'Lync Server 2013 : ajout de texte personnalisé dans des messages instantanés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb6746ea5897d779a202bc428b6c7259a1191f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Ajout de texte personnalisé dans des messages instantanés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-20_

Ajoutez une clause d’exclusion de responsabilité ou un avertissement au début de chaque conversation de messagerie instantanée Lync 2013 à l’aide des cmdlets **New-CSClientPolicy** ou **Set-CSClientPolicy** Lync Server Management Shell avec le paramètre imwarning.

Dans l’exemple suivant, la commande ajoute un rappel de sécurité en haut de la fenêtre de conversation chaque fois qu’une nouvelle conversation par messagerie instantanée est lancée:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Utilisez **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie aux utilisateurs. Pour plus d’informations, reportez-vous à **New-CSClientPolicy** et **Grant-CSClientPolicy** dans la documentation Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

