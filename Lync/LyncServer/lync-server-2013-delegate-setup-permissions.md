---
title: 'Lync Server 2013 : délégation des autorisations de configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0fcf148e5e3cc4003dac97e8ef5ca9f1b2e678a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Déléguer les autorisations de configuration dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Si vous ne souhaitez pas accorder l’appartenance au groupe administrateurs du domaine aux utilisateurs ou aux groupes qui déploient Lync Server 2013, vous pouvez permettre aux membres du groupe RTCUniversalServerAdmins d’exécuter l’applet de commande Windows PowerShell **Enable-CsTopology** sur les serveurs exécutant Lync Server 2013. Par défaut, les membres du groupe RTCUniversalServerAdmins n’ont pas la possibilité d’exécuter cette applet de commande. Vous accordez des droits et des autorisations d’administrateur pour exécuter **Enable-CsTopology** sur des serveurs exécutant Lync Server à l’aide de l’applet de commande **Grant-CsSetupPermission** et en spécifiant une unité d’organisation où se trouvent les objets ordinateur du serveur exécutant Lync Server 2013.

La préparation du domaine qui a lieu lors de l’installation de Lync Server n’ajoute pas automatiquement les autorisations qui permettent aux membres du groupe RTCUniversalServerAdmins d’exécuter la cmdlet Enable-CsTopology. Cela signifie que, par défaut, vous devez être administrateur de domaine pour activer une topologie. Pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’activer une topologie, vous devez exécuter l’applet de commande Grant-CsSetupPermissions. De plus, vous devrez exécuter cette applet de commande sur chaque conteneur Active Directory hébergeant des ordinateurs exécutant Lync Server.

Souvenez-vous que cette applet de commande n’accorde des autorisations qu’au groupe RTCUniversalServerAdmins. Il ne peut pas être utilisé pour accorder des autorisations à d’autres groupes de sécurité ou des utilisateurs individuels.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> est l’applet de commande clé pour permettre aux membres du groupe RTCUniversalServerAdmins de configurer et de déployer Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Pour ajouter la possibilité d’exécuter Enable-CsTopology dans le groupe RTCUniversalServerAdmins

1.  Ouvrez une session sur un serveur en tant que membre du groupe administrateurs du domaine pour le domaine sur lequel l’utilisateur délégué exécutera **Enable-CsTopology**.

2.  Ouvrez Lync Server 2013 Management Shell. Lync Server 2013 Management Shell est automatiquement installé sur chaque serveur frontal ou sur tout ordinateur sur lequel les outils d’administration Lync Server 2013 ont été installés. Pour plus d’informations sur Lync Server 2013 Management Shell, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) dans la documentation des opérations.

3.  Exécutez l’applet de commande suivante à partir de Lync Server 2013 Management Shell :
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Si l’unité d’organisation n’est pas de niveau supérieur, vous devez fournir le nom de domaine complet.

    
    </div>
    
    Dans l’exemple suivant, l’unité d’organisation est « Lync Servers », qui se trouve dans le domaine contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

