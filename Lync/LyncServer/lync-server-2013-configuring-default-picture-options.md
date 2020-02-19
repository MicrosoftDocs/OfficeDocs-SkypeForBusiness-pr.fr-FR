---
title: 'Lync Server 2013 : configuration des options d’image par défaut'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24d32ca52df9c75cf2a0816ff81bd5eaa775d22a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a>Configuration des options d’image par défaut dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-22_

Par défaut, les images des utilisateurs s’affichent automatiquement. Si les utilisateurs souhaitent masquer leurs images, ils peuvent sélectionner l’option **Masquer mon image** dans le client Lync. Toutefois, ce paramètre est ignoré par d’autres applications Office.

Si la possibilité d’afficher des images même lorsqu’elles sont désactivées par l’utilisateur est un problème, vous pouvez modifier les paramètres d’affichage des images Lync globalement ou pour un site ou un service afin que les images des utilisateurs ne soient pas affichées par défaut. Utilisez la cmdlet Lync Server Management Shell suivante pour que les images de l’utilisateur ne soient pas affichées, sauf si elles sélectionnent explicitement l’option **afficher mon image** dans le client :

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Pour plus d’informations sur cette applet de commande, voir [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) dans la documentation de Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

