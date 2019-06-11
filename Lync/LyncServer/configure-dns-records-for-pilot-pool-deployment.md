---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afde57a9ed64dbff537395ccef908ae44b86177d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configuration des enregistrements DNS pour le déploiement d’un pool pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-29_

Avant de déployer le pool de pilotes de Lync Server 2013, vous devez mettre à jour les entrées de l’hôte DNS pour le pool de pilotes. Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.

**Pour configurer les enregistrements d’un hôte DNS**

1.  Sur le serveur DNS (Domain Name System), cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.

3.  Cliquez sur **nouvel hôte (A ou AAAA)**.

4.  Cliquez sur **nom**, tapez le nom d’hôte du pool Lync Server 2013 (le nom de domaine est censé partir de la zone dans laquelle l’enregistrement est défini et qu’il n’est pas nécessaire d’entrer dans le cadre de l’enregistrement a).

5.  Cliquez sur **adresse IP**, tapez l’adresse IP de la liste frontale.

6.  Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.

7.  Lorsque vous avez terminé, cliquez sur **terminé**.

</div>

<span> </span>

</div>

</div>

</div>

