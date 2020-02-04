---
title: Migrer des périphériques analogiques
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e809db03cf098bea07f57673ddcbfc019e15f299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>Migrer des périphériques analogiques

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Lync Server prend en charge les appareils analogiques. Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Lync Server. Après avoir effectué une migration de Lync Server 2010 vers Lync Server 2013, vous devez également déplacer les objets de contact associés aux périphériques analogiques. Utilisez Lync Server Management Shell pour récupérer tous les objets de contact associés aux appareils analogiques Lync Server 2010, puis déplacez ces objets vers le pool Lync Server 2013.

<div>

## <a name="to-migrate-analog-devices"></a>Pour migrer des périphériques analogiques

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  À partir de la ligne de commande, tapez :
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Vérifiez que tous les objets de contact ont été déplacés vers le pool Lync Server 2013. À partir de la ligne de commande, tapez :
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Vérifiez que tous les objets de contact sont désormais associés au pool Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

