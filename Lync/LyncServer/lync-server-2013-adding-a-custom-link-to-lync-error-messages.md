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
ms.openlocfilehash: 3c9f15b72f105edf291007569999c549b8b2c841
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Ajout d’un lien personnalisé à des messages d’erreur Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Personnalisez les messages d’erreur de Lync 2013 en ajoutant un lien vers vos propres problèmes ou informations de support technique. Pour ce faire, utilisez les cmdlets **New-CSClientPolicy** ou **Set-CSClientPolicy** de l’environnement de commande Lync Server Management Shell avec le paramètre CustomLinkInErrorMessages. Le texte du lien personnalisé est « cliquez ici pour obtenir des rubriques d’aide auprès de votre administrateur » et il ne peut pas être personnalisé.

Par exemple, la commande suivante affiche le lien personnalisé dans la zone de note de bas de page de chaque message d’erreur Lync 2013 et définit la destination du lien surhttp://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Utilisez **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie aux utilisateurs. Pour plus d’informations, voir **New-CSClientPolicy** et **Grant-CSClientPolicy** dans la documentation de Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

