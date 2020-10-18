---
title: 'Lync Server 2013 : préparation de votre environnement pour VDI'
description: 'Lync Server 2013 : préparation de votre environnement pour VDI.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e90b9e0f09d3082a28406f1a1dc715285ee4d7e3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579910"
---
# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a>Préparation de votre environnement Lync Server 2013 pour VDI

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Pour préparer l’environnement pour le plug-in Lync VDI, l’administrateur doit effectuer les étapes suivantes.

1.  Dans Lync Server 2013, vérifiez que EnableMediaRedirection est défini sur TRUE pour tous les utilisateurs VDI. Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et la cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

2.  Sur l’ordinateur du centre de données, installez le client Lync 2013 sur toutes les machines virtuelles.

3.  Sur les ordinateurs locaux, installez le plug-in Lync VDI.

</div>

<span> </span>

</div>

</div>

</div>

