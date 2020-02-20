---
title: 'Lync Server 2013 : ajout d’un lien personnalisé à des messages d’erreur Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c02534c76a26313818e9ed4af8c51c31621bbd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="d333f-102">Ajout d’un lien personnalisé à des messages d’erreur Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d333f-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d333f-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d333f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d333f-104">Personnalisez les messages d’erreur de Lync 2013 en ajoutant un lien vers vos propres problèmes ou informations de support technique.</span><span class="sxs-lookup"><span data-stu-id="d333f-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="d333f-105">Pour ce faire, utilisez les cmdlets **New-CSClientPolicy** ou **Set-CSClientPolicy** de l’environnement de commande Lync Server Management Shell avec le paramètre CustomLinkInErrorMessages.</span><span class="sxs-lookup"><span data-stu-id="d333f-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="d333f-106">Le texte du lien personnalisé est « cliquez ici pour obtenir des rubriques d’aide auprès de votre administrateur » et il ne peut pas être personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d333f-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="d333f-107">Par exemple, la commande suivante affiche le lien personnalisé dans la zone de note de bas de page de chaque message d’erreur Lync 2013 et définit la destination du lien surhttp://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="d333f-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="d333f-108">Utilisez **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d333f-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="d333f-109">Pour plus d’informations, voir **New-CSClientPolicy** et **Grant-CSClientPolicy** dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d333f-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

