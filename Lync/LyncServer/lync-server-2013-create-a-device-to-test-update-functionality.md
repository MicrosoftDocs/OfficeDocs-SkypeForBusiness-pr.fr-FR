---
title: 'Lync Server 2013 : création d’un appareil pour tester la fonctionnalité de mise à jour'
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
ms.openlocfilehash: bbf4d45edce186819241ce6244e1ea1cd6677bfa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501971"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Créer un appareil pour tester la fonctionnalité de mise à jour dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier la fonctionnalité des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement Lync Server) ou au sein d’un même site. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un périphérique, il apparaît dans la liste sur la page **périphérique de test** du panneau de configuration Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Pour ajouter un périphérique de test

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Périphérique de test**.

3.  Cliquez sur **Nouveau**, puis sur **Périphérique de test global** ou **Périphérique de test sur site**.

4.  Effectuez l’une des opérations suivantes :
    
      - Si vous avez cliqué sur **Périphérique de test global**, passez à l’étape suivante.
    
      - Si vous avez cliqué sur **Périphérique de test sur site**, sélectionnez un site dans la liste des sites disponibles, puis cliquez sur **OK**.

5.  Dans **Nouveau périphérique de test**, tapez un nom de périphérique dans **Nom du périphérique**.

6.  Sous **Type d’identificateur**, cliquez sur **Adresse MAC** ou **Numéro de série**.

7.  Dans la zone **Identificateur unique**, tapez l’adresse MAC ou le numéro de série du périphérique.

8.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Création de périphériques de test à l’aide d’applets de commande Windows PowerShell

Les périphériques de test peuvent être créés à l’aide de Windows PowerShell et de l’applet de commande New-CsTestDevice. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

Lors de la création de périphériques de test à l’aide de cette applet de commande, vous devez effectuer deux opérations :

  - spécifier MACAddress ou SerialNumber comme IdentifierType ;

  - inclure l’étendue lorsque vous spécifiez l’identité du périphérique. Pour créer un périphérique au niveau global, utilisez une syntaxe telle que celle-ci :
    
        -Identity "global/WindowsPhone"
    
    Pour créer un périphérique de test au niveau de l’étendue Site, utilisez une syntaxe semblable à celle-ci :
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Pour créer un périphérique de test à l’aide de l’adresse MAC

  - Cette commande crée un périphérique de test au niveau de l’étendue Site et utilise l’adresse MAC comme IdentifierType :
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Pour créer un périphérique de test à l’aide du numéro de série

  - Cette commande crée un périphérique de test au niveau de l’étendue Site (pour le site Redmond) et utilise le numéro de série comme IdentifierType :
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

