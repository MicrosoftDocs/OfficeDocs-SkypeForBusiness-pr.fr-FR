---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e171e821d2fcf5c773321ada3a5b107b28314699
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Mettre à jour les enregistrements SRV DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-29_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.

Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Lync Server 2013. Une fois tous les utilisateurs déplacés vers Lync Server 2013, mais avant la désactivation du pool ou du réalisateur du serveur Lync Server 2010, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP. Cette procédure part du principe que votre DNS interne comporte des zones pour vos domaines d’utilisateur SIP.

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

