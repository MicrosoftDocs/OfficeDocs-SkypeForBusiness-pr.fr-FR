---
title: 'Lync Server 2013 : activer ou désactiver le contrôle de version du client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Activer ou désactiver le contrôle de version du client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les paramètres de configuration de la version du client permettent d’activer ou de désactiver le contrôle de version du client, globalement ou pour des sites spécifiques. La configuration de la version du client global s’installe avec Lync Server 2013 et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement complet du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version de client en vigueur sont prises en compte lorsque les utilisateurs essaient de se connecter. Vous pouvez désactiver la configuration de la version du client global si vous ne souhaitez pas que le contrôle de version du client se produise. Vous pouvez activer ou désactiver le contrôle de version du client via le panneau de configuration de Lync Server 2013 ou Lync Server 2013 Management Shell.

<div>


> [!NOTE]  
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes ne sont affectés que par les stratégies globales.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Pour activer ou désactiver le contrôle de version du client à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .

4.  Procédez comme suit :
    
      - Pour activer ou désactiver globalement le contrôle de version, double-cliquez sur la configuration **globale** , puis modifiez les paramètres.
    
      - Pour activer ou désactiver le contrôle de version du client pour un site particulier, cliquez sur **nouveau**, sélectionnez le site, cliquez sur **OK**, puis modifiez les paramètres du site.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation du contrôle de version du client à l’aide des cmdlets Windows PowerShell

Vous pouvez activer ou désactiver le contrôle de version du client à l’aide de l’applet **de contrôle Set-CsClientVersionConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-enable-client-versioning"></a>Pour activer le contrôle de version du client

  - Vous pouvez activer le contrôle de version du client en définissant la propriété **Enabled** sur True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Pour désactiver le contrôle de version du client

  - Vous pouvez désactiver le contrôle de version du client en définissant la propriété **Enabled** sur false ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

