---
title: 'Lync Server 2013 : configuration des options d’image par défaut'
description: 'Lync Server 2013 : configuration des options d’image par défaut.'
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
ms.openlocfilehash: 6261aca82b4c71eb8e0573e8d2adbfc008e743fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558000"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="21954-103">Configuration des options d’image par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21954-103">Configuring default picture options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21954-104">_**Dernière modification de la rubrique :** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="21954-104">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="21954-105">Par défaut, les images des utilisateurs s’affichent automatiquement.</span><span class="sxs-lookup"><span data-stu-id="21954-105">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="21954-106">Si les utilisateurs souhaitent masquer leurs images, ils peuvent sélectionner l’option **Masquer mon image** dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="21954-106">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="21954-107">Toutefois, ce paramètre est ignoré par d’autres applications Office.</span><span class="sxs-lookup"><span data-stu-id="21954-107">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="21954-108">Si la possibilité d’afficher des images même lorsqu’elles sont désactivées par l’utilisateur est un problème, vous pouvez modifier les paramètres d’affichage des images Lync globalement ou pour un site ou un service afin que les images des utilisateurs ne soient pas affichées par défaut.</span><span class="sxs-lookup"><span data-stu-id="21954-108">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="21954-109">Utilisez la cmdlet Lync Server Management Shell suivante pour que les images de l’utilisateur ne soient pas affichées, sauf si elles sélectionnent explicitement l’option **afficher mon image** dans le client :</span><span class="sxs-lookup"><span data-stu-id="21954-109">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="21954-110">Pour plus d’informations sur cette applet de commande, voir [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="21954-110">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

