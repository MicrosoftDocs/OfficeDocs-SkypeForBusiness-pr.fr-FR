---
title: Importer des stratégies et des paramètres
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dde4cfdc2f027c095cd6ad95582a130d047d3c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>Importer des stratégies et des paramètres

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Après avoir fusionné les informations de topologie Office Communications Server 2007 R2 avec votre pool pilote Lync Server 2013, vous devez exécuter une cmdlet Lync Server 2013 Management Shell pour migrer vos stratégies et paramètres de configuration Office Communications Server 2007 R2. à votre pool pilote Lync Server 2013.

L’applet de commande **Import-applet cslegacyconfiguration** importe des stratégies, des itinéraires de communications vocales, des plans de numérotation, des URL d’Office Communicator Web Access et des numéros d’accès entrant vers Lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Pour migrer les stratégies et les paramètres

1.  Sur le serveur frontal Lync Server 2013, démarrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez le code suivant :
    
        Import-CsLegacyConfiguration
    
    Une fois les stratégies importées, utilisez la procédure suivante pour afficher les stratégies importées dans le panneau de configuration Lync Server.

</div>

<div>

## <a name="to-view-imported-policies"></a>Pour afficher les stratégies importées

1.  Ouvrez le panneau de configuration Lync Server 2013.

2.  Cliquez sur **Routage des communications vocales** et affichez les stratégies importées.

3.  Cliquez sur **Conférence** et affichez les stratégies importées.

4.  Cliquez sur **Fédération et accès externe** et affichez les stratégies importées.

5.  Cliquez sur **Surveillance et archivage** et affichez les stratégies importées.

</div>

</div>

<span> </span>

</div>

</div>

</div>

