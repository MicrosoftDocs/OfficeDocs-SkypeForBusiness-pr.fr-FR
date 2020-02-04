---
title: 'Lync Server 2013 : créer un appareil pour tester la fonctionnalité de mise à jour'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b197c4b42542310746568fe351f98c7d991509cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Créer un appareil pour tester la fonctionnalité de mise à jour dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester globalement un appareil (dans tout votre environnement Lync Server) ou sur un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page **périphérique de test** du panneau de configuration de Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Pour ajouter un périphérique de test

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation gauche, cliquez sur **clients**, puis sur **tester l’appareil**.

3.  Cliquez sur **nouveau**, puis sur **périphérique de test global** ou **appareil de test de site**.

4.  Effectuez l’une des actions suivantes :
    
      - Si vous avez cliqué sur **périphérique de test global**, passez à l’étape suivante.
    
      - Si vous avez cliqué sur l' **appareil de test de site**, sélectionnez un site dans la liste des sites disponibles, puis cliquez sur **OK**.

5.  Dans **nouvel appareil de test**, tapez un nom pour l’appareil dans nom de l' **appareil**.

6.  Sous **type d’identificateur**, cliquez sur **adresse Mac** ou **numéro de série**.

7.  Dans la zone **identificateur unique** , tapez l’adresse Mac ou le numéro de série de l’appareil.

8.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Création de périphériques de test à l’aide d’applets de contrôle Windows PowerShell

Les appareils de test peuvent être créés à l’aide de Windows PowerShell et de l’applet de contrôle New-CsTestDevice. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

Lors de la création de périphériques de test à l’aide de cette applet de contrôle, vous devez effectuer deux opérations :

  - Spécifiez MACAddress ou SerialNumber en tant que IdentifierType.

  - Incluez l’étendue lors de la spécification de l’identité de l’appareil. Pour créer un nouvel appareil à l’étendue globale, utilisez une syntaxe semblable à celle-ci :
    
        -Identity "global/WindowsPhone"
    
    Pour créer un périphérique de test à l’étendue du site, utilisez une syntaxe semblable à celle-ci :
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Pour créer un périphérique de test à l’aide de l’adresse MAC

  - Cette commande crée un appareil de test à l’étendue globale et utilise l’adresse MAC comme IdentifierType :
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Pour créer un périphérique de test à l’aide du numéro de série

  - Cette commande crée un nouveau périphérique de test sur l’étendue du site (pour le site de Redmond) et utilise le numéro de série en tant que IdentifierType :
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

