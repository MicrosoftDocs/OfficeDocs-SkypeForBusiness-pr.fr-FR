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
ms.openlocfilehash: 7c56d7ae13be9afa3af7e4732242a86f4be4c458
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Activer ou désactiver la gestion de l’accès à chaud dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Vous pouvez configurer des téléphones communs en tant que *téléphones de bureau à chaud*. Les téléphones de bureau à chaud permettent aux utilisateurs de se connecter à leur propre compte d’utilisateur et, après leur ouverture de session, d’utiliser les fonctionnalités du serveur Lync et leurs propres paramètres de profil utilisateur. La gestion de l’accès à chaud est gérée en utilisant les stratégies client : pour activer ou désactiver la gestion de l’accès à chaud, vous devez modifier les stratégies de client utilisées par les téléphones de votre zone commune. Pour plus d’informations sur l’identification des stratégies de conférence qui ont été affectées à vos téléphones communs, voir afficher les informations sur le [téléphone de zone commune dans Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Vous utilisez le paramètre EnableHotdesking de la cmdlet **New-CSClientPolicy** ou de l’applet de connexion **Set-CSClientPolicy** pour activer ou désactiver la fonction Hot Desk sur un téléphone, comme suit. Exécutez ces applets de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>


<div>

## <a name="enabling-hot-desking"></a>Activation de l’assistance à chaud

  - Pour activer le Bureau à chaud pour un téléphone de zone commune, vous devez modifier la stratégie client qui a été attribuée à ce téléphone (ou collection de téléphones).
    
    Une fois que vous avez identifié la stratégie qui doit être modifiée, l’étape suivante consiste à utiliser l’applet de cmdlet **Set-CsClientPolicy** pour définir le paramètre EnableHotdesking sur true. Par exemple :
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Vous pouvez également utiliser l’applet de **nouvelle applet de nouveau-CsClientPolicy** pour créer une nouvelle stratégie client qui autorise la gestion à chaud. Par exemple :
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Une fois cette stratégie créée, vous devez l’attribuer aux téléphones communs appropriés. Pour plus d’informations, consultez <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">attribuer des stratégies dans Lync Server 2013 à un téléphone de zone commune</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Désactivation de l’assistance à chaud

  - Pour désactiver le téléphone de bureau à chaud pour un téléphone standard, réinitialisez le paramètre EnableHotdesking de l’applet de connexion **Set-CsClientPolicy** sur la valeur par défaut false. Par exemple :
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Pour plus d’informations, consultez les rubriques d’aide pour la cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et l’applet de connexion [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

