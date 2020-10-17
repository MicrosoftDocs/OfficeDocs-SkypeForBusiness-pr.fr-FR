---
title: 'Lync Server 2013 : configuration du chiffrement multimédia pour les fournisseurs publics'
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
ms.openlocfilehash: 45a6a3dcccc766e9905017c0b35949ab4ff6894d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520601"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Configurer le chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-12_

Si vous implémentez la Fédération audio/vidéo (A/V) avec Windows Live Messenger, vous devez modifier deux paramètres : le niveau de chiffrement Lync Server et la stratégie EnablePublicCloudAccess. Par défaut, le niveau de chiffrement est Requis. Vous devez définir ce paramètre sur Pris en charge. Si la stratégie EnablePublicCloudAccess a la valeur False, vous devez lui affecter la valeur **True**. Vous pouvez effectuer cette opération à partir de Lync Server Management Shell.

<div>

## <a name="configure-federation-for-windows-live"></a>Configurer la fédération pour Windows Live

1.  Démarrez Lync Server Management Shell sur le serveur frontal : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  À l’invite de commandes, tapez les commandes suivantes :
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Cette étape est obligatoire car Windows Live Messenger ne prend pas en charge le chiffrement de l’audio/vidéo. La commande affecte un paramètre de prise en charge du chiffrement à votre stratégie globale au lieu d’exiger le chiffrement des données audio/vidéo. Les clients qui prennent en charge le chiffrement utilisent toujours le chiffrement, tel que Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

