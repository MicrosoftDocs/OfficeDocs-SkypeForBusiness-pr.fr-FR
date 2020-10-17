---
title: Conditions préalables
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f81299b2efdde3be262439528409d89abf369f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509131"
---
# <a name="prerequisites"></a>Conditions préalables

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-19_

Il existe différentes exigences en matière de configuration du matériel, des logiciels et des systèmes, dont vous aurez besoin pour exécuter l’outil de contrainte et de performances de Lync Server 2013.

<div>

## <a name="client-hardware-requirements"></a>Configuration matérielle requise pour le client

Pour exécuter l’outil de contrainte et de performances de Lync Server 2013 sur votre déploiement Lync Server 2013, tous les 4 500 utilisateurs dont la charge doit être simulée, vous devez disposer d’au moins un ordinateur dédié répondant à la configuration matérielle minimale requise suivante :

  - carte réseau 1 Gigabit

  - 8 Go de RAM

  - 2 unités centrales (UC) double cœur

</div>

<div>

## <a name="client-software-requirements"></a>Configuration logicielle requise pour le client

Pour exécuter l’outil de contrainte et de performances de Lync Server 2013 sur votre déploiement Lync Server 2013, les systèmes d’exploitation pris en charge sont les suivants :

  - Système d’exploitation Windows Server 2012

  - Système d’exploitation Windows Server 2008 (version 64 bits)

Votre ordinateur client doit répondre à la configuration logicielle requise suivante :

  - [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) Runtime doit être installé.

  - Sur Windows Server 2008/Windows Server 2012, la fonctionnalité expérience utilisateur doit être activée.

  - Le [package redistribuable de Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64) doit être installé sur votre ordinateur.

  - Un déploiement de Lync Server 2013 entièrement configuré.

<div>


> [!IMPORTANT]  
> Les bibliothèques Microsoft Unified Communications Managed API (UCMA) 4,0 sont incluses dans le package d’installation, de sorte que UCMA n’est pas obligatoire et ne doit pas être installé sur les ordinateurs clients.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Configuration requise

Les ordinateurs qui exécuteront l’outil de contrainte et de performances de Lync Server 2013 doivent être configurés conformément aux exigences suivantes :

1.  Vous devez être connecté en tant que membre du groupe de domaine ou du groupe Administrateurs local.

2.  Lync Server 2013 stress and Performance Tool (LyncPerfTool.exe) ne peut pas être exécuté sur un ordinateur qui exécute également les composants Lync Server 2013.

3.  Vous devez exécuter l’outil de création d’utilisateurs Lync Server 2013 (UserProvisioningTool.exe) sur le serveur frontal ou sur le serveur Standard Edition où les comptes d’utilisateur doivent résider. Lorsque l’outil est exécuté plusieurs fois, chaque utilisateur activé pour les communications unifiées de Microsoft doit disposer d’un numéro de téléphone unique.

4.  La taille du fichier d’échange doit être gérée par le système ou au moins 1,5 fois la quantité de RAM sur le système.

</div>

</div>

<span> </span>

</div>

</div>

</div>

