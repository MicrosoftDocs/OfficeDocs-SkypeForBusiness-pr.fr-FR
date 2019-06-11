---
title: 'Lync Server 2013 : Délégation des autorisations de configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7df00740ac971fd56e289da04ca43abb1619329
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Délégation des autorisations de configuration dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-05_

Si vous ne voulez pas attribuer l’appartenance au groupe administrateurs de domaine à des utilisateurs ou des groupes qui déploient Lync Server 2013, vous pouvez permettre aux membres du groupe RTCUniversalServerAdmins d’exécuter l’applet de contrôle Windows PowerShell **Enable-CsTopology** sur serveurs exécutant Lync Server 2013. Par défaut, les membres du groupe RTCUniversalServerAdmins n’ont pas la possibilité d’exécuter cette cmdlet. Vous accordez des droits d’administrateur et des autorisations pour exécuter **Enable-CsTopology** sur des serveurs exécutant Lync Server à l’aide de l’applet de passe **Grant-CsSetupPermission** et spécifiant une unité d’organisation (UO) sur laquelle des objets d’ordinateur s’exécutent sur le serveur. Lync Server 2013 est disponible.

La préparation du domaine qui intervient lors de l’installation de Lync Server n’ajoute pas automatiquement les autorisations qui permettent aux membres du groupe RTCUniversalServerAdmins d’exécuter l’applet de demande Enable-CsTopology. Cela signifie que, par défaut, vous devez être un administrateur de domaine pour pouvoir activer une topologie. Pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’activer une topologie, vous devez exécuter l’applet de la cmdlet Grant-CsSetupPermissions. Par ailleurs, vous devrez exécuter cette cmdlet sur chaque conteneur Active Directory qui héberge des ordinateurs exécutant Lync Server.

Gardez à l’esprit que cette applet de cmdlet accorde uniquement des autorisations au groupe RTCUniversalServerAdmins; l’applet de cmdlet ne peut pas être utilisée pour accorder des autorisations à d’autres groupes de sécurité ou à des utilisateurs individuels.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> est l’applet de clé pour permettre aux membres du groupe RTCUniversalServerAdmins de configurer et de déployer Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Pour ajouter la possibilité d’exécuter Enable-CsTopology au groupe RTCUniversalServerAdmins

1.  Connectez-vous à un serveur en tant que membre du groupe Domain Admins pour le domaine sur lequel l’utilisateur délégué exécutera **Enable-CsTopology**.

2.  Ouvrez Lync Server 2013 Management Shell. Lync Server 2013 Management Shell est automatiquement installé sur chaque serveur frontal ou sur tout ordinateur sur lequel sont installés les outils d’administration de Lync Server 2013. Pour plus d’informations sur Lync Server 2013 Management Shell, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) dans la documentation opérations.

3.  Exécutez l’applet de commande suivante à partir de Lync Server 2013 Management Shell:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Si l’unité d’organisation n’est pas de niveau supérieur, vous devez fournir le nom de domaine complet.

    
    </div>
    
    Dans l’exemple suivant, l’unité d’organisation est «Lync Servers», qui se trouve dans le domaine contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

