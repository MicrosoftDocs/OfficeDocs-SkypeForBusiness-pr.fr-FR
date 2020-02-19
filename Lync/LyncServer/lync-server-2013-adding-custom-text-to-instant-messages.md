---
title: 'Lync Server 2013 : ajout de texte personnalisé aux messages instantanés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ebaaaa693248cd11ebcb663692fa2805cdce20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="741ad-102">Ajout de texte personnalisé aux messages instantanés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="741ad-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="741ad-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="741ad-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="741ad-104">Ajoutez une clause d’exclusion de responsabilité ou un avertissement au début de chaque conversation de messagerie instantanée Lync 2013 à l’aide des cmdlets **New-CSClientPolicy** ou **Set-CSClientPolicy** de l’environnement de commande Lync Server Management Shell avec le paramètre imwarning.</span><span class="sxs-lookup"><span data-stu-id="741ad-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="741ad-105">La commande de l’exemple suivant ajoute un rappel de sécurité en haut de la fenêtre de conversation à chaque fois qu’une nouvelle conversation de messagerie instantanée débute :</span><span class="sxs-lookup"><span data-stu-id="741ad-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="741ad-106">Utilisez **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="741ad-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="741ad-107">Pour plus d’informations, voir **New-CSClientPolicy** et **Grant-CSClientPolicy** dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="741ad-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

