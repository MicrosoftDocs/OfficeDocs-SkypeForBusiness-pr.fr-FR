---
title: 'Lync Server 2013 : activation ou désactivation de l’assistance à chaud'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb052f3a0743edac47ccfbe3786943820c59f78f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515542"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Activation ou désactivation de la connexion à chaud dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Vous pouvez configurer des téléphones de partie commune en tant que *téléphones de bureau à chaud*. Avec les téléphones de bureau à chaud, les utilisateurs peuvent se connecter à leur propre compte d’utilisateur et, une fois qu’ils sont connectés, utiliser les fonctionnalités de Lync Server et leurs propres paramètres de profil utilisateur. La gestion de l’accès à chaud est gérée à l’aide de stratégies de client : pour activer ou désactiver la connexion à chaud, vous devez modifier les stratégies client utilisées par vos téléphones de partie commune. Pour plus d’informations sur la façon de déterminer les stratégies de conférence qui ont été affectées à vos téléphones de partie commune, voir [View Common Area Phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Vous utilisez le paramètre EnableHotdesking de la cmdlet **New-CSClientPolicy** ou l’applet de commande **Set-CSClientPolicy** pour activer ou désactiver la connexion à chaud sur un téléphone, comme suit. Exécutez ces applets de commande à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>


<div>

## <a name="enabling-hot-desking"></a>Activation de l’assistance à chaud

  - Pour activer la gestion d’urgence pour un téléphone de partie commune, vous devez modifier la stratégie de client qui a été attribuée à ce téléphone (ou à la collection de téléphones).
    
    Une fois que vous avez identifié la stratégie qui doit être modifiée, l’étape suivante consiste à utiliser l’applet de commande **Set-CsClientPolicy** pour définir le paramètre EnableHotdesking sur true. Par exemple :
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Vous pouvez également utiliser la cmdlet **New-CsClientPolicy** pour créer une nouvelle stratégie client qui permet la connexion à chaud. Par exemple :
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Une fois cette stratégie créée, vous devez l’affecter aux téléphones de la partie commune appropriés. Pour plus d’informations, consultez <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">la rubrique Assign Policies in Lync Server 2013 à un téléphone de partie commune</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Désactivation de l’assistance à chaud

  - Pour désactiver la connexion à chaud pour un téléphone de partie commune, réinitialisez le paramètre EnableHotdesking de la cmdlet **Set-CsClientPolicy** sur la valeur par défaut false. Par exemple :
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et la cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

