---
title: Conditions requises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74603ed20fe144ca89d3ac13bc00fef0e7d6ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>Conditions requises

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-19_

Il existe différentes exigences matérielles, logicielles et de configuration du système requises pour exécuter l’outil de stress et de performance de Lync Server 2013.

<div>

## <a name="client-hardware-requirements"></a>Configuration matérielle requise pour le client

Pour exécuter l’outil de stress et de performance Lync Server 2013 sur votre déploiement Lync Server 2013, pour tous les utilisateurs de 4 500 dont le chargement doit être simulé, vous devez disposer d’au moins un ordinateur dédié qui répond à la configuration minimale requise suivante:

  - carte réseau 1 gigabit

  - 8 Go de mémoire vive (RAM)

  - 2 unités centrales double cœur (UC)

</div>

<div>

## <a name="client-software-requirements"></a>Configuration logicielle requise pour le client

Pour exécuter l’outil de stress et de performance Lync Server 2013 sur votre déploiement Lync Server 2013, les systèmes d’exploitation pris en charge sont les suivants:

  - Système d’exploitation Windows Server 2012

  - Système d’exploitation Windows Server 2008 (64-bit Edition)

Votre ordinateur client doit présenter la configuration logicielle requise suivante:

  - [Microsoft .NET Framework 4,5](http://go.microsoft.com/fwlink/?linkid=143212) Runtime doit être installé sur votre ordinateur.

  - Sur Windows Server 2008/Windows Server 2012, la fonctionnalité expérience de bureau doit être activée.

  - Le [package redistribuable 2012 Microsoft Visual C++](http://go.microsoft.com/fwlink/?linkid=143216) (x64) doit être installé.

  - Un déploiement entièrement configuré de Lync Server 2013.

<div>


> [!IMPORTANT]  
> Les bibliothèques 4,0 (Unified Communications Managed API) de Microsoft sont incluses dans le package d’installation, de sorte que UCMA n’est pas obligatoire et ne doit pas être installé sur les ordinateurs clients.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Configuration requise

Les ordinateurs exécutant l’outil de stress et de performances de Lync Server 2013 doivent être configurés conformément à la configuration requise suivante:

1.  Vous devez être connecté en tant que membre du groupe Domain ou admins locaux.

2.  L’outil de stress et de performance Lync Server 2013 (LyncPerfTool. exe) ne peut pas être exécuté sur un ordinateur qui exécute également les composants Lync Server 2013.

3.  Vous devez exécuter l’outil de création d’utilisateurs de Lync Server 2013 (UserProvisioningTool. exe) sur le serveur frontal ou sur le serveur Standard Edition Server sur lequel résideront les comptes d’utilisateurs. Lorsque l’outil s’exécute plusieurs fois, chaque utilisateur autorisé à utiliser Microsoft Unified Communications doit avoir un numéro de téléphone unique.

4.  La taille du fichier de page doit être gérée par le système, ou être au moins 1,5 fois la quantité de RAM sur le système.

</div>

</div>

<span> </span>

</div>

</div>

</div>

