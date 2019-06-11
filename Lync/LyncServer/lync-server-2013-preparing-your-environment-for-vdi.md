---
title: 'Lync Server 2013 : Préparation de l’environnement pour VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5081d1267b9de521ebd17fa5f3ec5ae57a912970
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a>Préparation de l’environnement Lync Server 2013 pour VDI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-22_

Pour préparer l’environnement pour le plug-in Lync VDI, l’administrateur doit procéder comme suit.

1.  Dans Lync Server 2013, assurez-vous que EnableMediaRedirection est défini sur TRUE pour tous les utilisateurs de VDI. Pour plus d’informations, consultez les rubriques d’aide pour la cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et l’applet de connexion [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

2.  Sur l’ordinateur du centre de données, installez le client 2013 Lync sur toutes les machines virtuelles.

3.  Sur l’ordinateur local, installez le plug-in Lync VDI.

</div>

<span> </span>

</div>

</div>

</div>

