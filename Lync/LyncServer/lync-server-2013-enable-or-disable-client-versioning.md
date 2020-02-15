---
title: 'Lync Server 2013 : activation ou désactivation du contrôle de version du client'
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
ms.openlocfilehash: d86fc41847485cbe797da9e9c9ace4a0a8794280
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Activer ou désactiver le contrôle de version du client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les paramètres de configuration de la version du client permettent d’activer ou de désactiver le contrôle de version du client, soit globalement, soit pour des sites particuliers. La configuration de la version du client global s’installe avec Lync Server 2013 et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration de version du client globale si vous ne souhaitez pas que le contrôle de version du client se produise. Vous pouvez activer ou désactiver le contrôle de version du client à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>


> [!NOTE]  
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Pour activer ou désactiver le contrôle de version du client à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .

4.  Procédez comme suit :
    
      - Pour activer ou désactiver globalement le contrôle de version du client, double-cliquez sur la configuration **globale** , puis modifiez les paramètres.
    
      - Pour activer ou désactiver le contrôle de version du client pour un site particulier, cliquez sur **nouveau**, sélectionnez le site, cliquez sur **OK**, puis modifiez les paramètres du site.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation du contrôle de version du client à l’aide des applets de commande Windows PowerShell

Vous pouvez activer ou désactiver le contrôle de version du client à l’aide de la cmdlet **Set-CsClientVersionConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-enable-client-versioning"></a>Pour activer le contrôle de version du client

  - Vous pouvez activer le contrôle de version du client en affectant à la propriété **Enabled** la valeur True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Pour désactiver le contrôle de version du client

  - Vous pouvez désactiver le contrôle de version du client en affectant à la propriété **Enabled** la valeur false ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

