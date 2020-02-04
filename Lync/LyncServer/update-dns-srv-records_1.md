---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 927bdab6721583fd744f68969a852f29ba478027
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Mettre à jour les enregistrements SRV DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.

Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Lync Server 2013. Une fois tous les utilisateurs déplacés vers Lync Server 2013, mais avant la désactivation du pool ou du réalisateur d’ancienne version d’Office Communications Server 2007 R2, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP. Cette procédure part du principe que votre DNS interne comporte des zones pour vos domaines d’utilisateur SIP.

**Pour configurer un enregistrement SRV DNS**

1.  Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, développez le domaine SIP dans lequel Lync Server 2013 est installé, puis accédez au paramètre ** \_TCP** .

3.  Dans le volet droit, cliquez avec le bouton droit sur ** \_sipinternaltls** , puis sélectionnez **Propriétés**.

4.  Dans la liste des **hôtes proposant ce service**, mettez à jour le nom de domaine complet (FQDN) du serveur pour qu’il pointe sur le pool Lync Server 2013.

5.  Cliquez sur **OK**.

**Pour vérifier que le nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition peut être résolu**

1.  Connectez-vous à un ordinateur client dans le domaine.

2.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

3.  Dans la zone **ouvrir** , tapez **cmd**, puis cliquez sur **OK**.

4.  À l’invite de commandes, tapez **nslookup** \<FQDN du pool\> frontal ou \<du FQDN du serveur\>Standard Edition, puis appuyez sur entrée.

5.  Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).

</div>

<span> </span>

</div>

</div>

</div>

