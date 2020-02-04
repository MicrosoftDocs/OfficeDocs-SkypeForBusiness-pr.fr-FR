---
title: 'Lync Server 2013 : Configuration du chiffrement multimédia pour les fournisseurs publics'
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
ms.openlocfilehash: 6d4ab36d19726a6092f978a2ac2a119b248cd0f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Configuration du chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-12_

Si vous implémentez une Fédération audio/vidéo (A/V) avec Windows Live Messenger, vous devez modifier deux paramètres : le niveau de chiffrement de Lync Server et la stratégie EnablePublicCloudAccess. Par défaut, le niveau de cryptage est défini sur obligatoire. Vous devez définir ce paramètre sur pris en charge. Si la stratégie EnablePublicCloudAccess est définie sur false, elle doit être définie sur **true**. Vous pouvez le faire à partir de Lync Server Management Shell.

<div>

## <a name="configure-federation-for-windows-live"></a>Configurer la Fédération pour Windows Live

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
    > Cette étape est obligatoire, car Windows Live Messenger ne prend pas en charge le chiffrement audio/vidéo. La commande définit votre stratégie globale sur un paramètre de chiffrement du support au lieu de nécessiter le chiffrement des données audio/vidéo. Les clients prenant en charge le chiffrement utilisent toujours le chiffrement, tel que Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

