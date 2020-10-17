---
title: 'Lync Server 2013 : afficher les paramètres de configuration de la version du client'
description: 'Lync Server 2013 : afficher les paramètres de configuration de la version du client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04fc25a1ab4904cbc6ca7871e1568ac8bc488bdf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572500"
---
# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a>Afficher les paramètres de configuration de la version du client dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version du client global s’installe avec Lync Server 2013 et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client qui sont en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez afficher les paramètres de configuration de la version du client à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>


> [!NOTE]  
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Pour afficher les paramètres de configuration de la version du client à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .

4.  Double-cliquez sur le nom de la version du client que vous souhaitez afficher.

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Affichage des paramètres de configuration de version des clients à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les paramètres de configuration de la version du client à l’aide de la cmdlet **Get-CsClientVersionConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-client-version-configuration-information"></a>Pour afficher les informations de configuration de la version du client

  - Pour afficher des informations sur tous les paramètres de configuration de la version du client, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsClientVersionConfiguration
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

