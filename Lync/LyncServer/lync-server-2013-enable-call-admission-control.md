---
title: 'Lync Server 2013 : activer le contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1776cc173d7ddec50aae34e8316844d14f67b009
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a>Activer le contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Une fois que vous avez configuré vos paramètres réseau pour le déploiement du contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels afin de mettre en œuvre vos stratégies de bande passante.

Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [Get-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>Pour activer le contrôle d’admission des appels à l’aide de Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsNetworkConfiguration pour activer le contrôle d’admission des appels dans votre réseau. Par exemple, exécutez :
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Si vous souhaitez désactiver le contrôle d’admission des appels dans votre réseau, exécutez la commande suivante :
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>Pour activer le contrôle d’admission des appels à l’aide du panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Global**.

4.  Cliquez sur **Global** dans la liste, puis sélectionnez **Afficher les détails** dans le menu **Edition**.

5.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**.
    
    <div>
    

    > [!NOTE]  
    > Si vous souhaitez désactiver le contrôle d’admission des appels dans tout votre déploiement, désactivez cette case à cocher.

    
    </div>

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

