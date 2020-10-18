---
title: 'Lync Server 2013 : configuration du chiffrement multimédia pour les fournisseurs publics'
description: 'Lync Server 2013 : configurez le chiffrement multimédia pour les fournisseurs publics.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177c19f151b67d741c7e26506f7ebc98b3ce831a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577620"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="6abfe-103">Configurer le chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abfe-103">Configure media encryption for public providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6abfe-104">_**Dernière modification de la rubrique :** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="6abfe-104">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="6abfe-105">Si vous implémentez la Fédération audio/vidéo (A/V) avec Windows Live Messenger, vous devez modifier deux paramètres : le niveau de chiffrement Lync Server et la stratégie EnablePublicCloudAccess.</span><span class="sxs-lookup"><span data-stu-id="6abfe-105">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="6abfe-106">Par défaut, le niveau de chiffrement est Requis.</span><span class="sxs-lookup"><span data-stu-id="6abfe-106">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="6abfe-107">Vous devez définir ce paramètre sur Pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6abfe-107">You must change this setting to Supported.</span></span> <span data-ttu-id="6abfe-108">Si la stratégie EnablePublicCloudAccess a la valeur False, vous devez lui affecter la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="6abfe-108">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="6abfe-109">Vous pouvez effectuer cette opération à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6abfe-109">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="6abfe-110">Configurer la fédération pour Windows Live</span><span class="sxs-lookup"><span data-stu-id="6abfe-110">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="6abfe-111">Démarrez Lync Server Management Shell sur le serveur frontal : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6abfe-111">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6abfe-112">À l’invite de commandes, tapez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6abfe-112">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="6abfe-113">Cette étape est obligatoire car Windows Live Messenger ne prend pas en charge le chiffrement de l’audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="6abfe-113">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="6abfe-114">La commande affecte un paramètre de prise en charge du chiffrement à votre stratégie globale au lieu d’exiger le chiffrement des données audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="6abfe-114">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="6abfe-115">Les clients qui prennent en charge le chiffrement utilisent toujours le chiffrement, tel que Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6abfe-115">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

