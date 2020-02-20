---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 894fac5341af8882db8ba4bb5fdbbc16b2a19dd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Mettre à jour les enregistrements SRV DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Lync Server 2013. Une fois que tous les utilisateurs ont été déplacés vers Lync Server 2013, mais avant que le pool ou le directeur de Lync Server 2010 hérité ne soit désactivé, vous devez mettre à jour les enregistrements SRV DNS dans votre DNS interne pour chaque domaine SIP. Cela présuppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.

**Pour configurer un enregistrement DNS SRV**

1.  Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, développez le domaine SIP dans lequel Lync Server 2013 est installé, puis accédez au paramètre ** \_TCP** .

3.  Dans le volet droit, cliquez avec le bouton droit sur ** \_sipinternaltls** , puis sélectionnez **Propriétés**.

4.  Dans **hôte offrant ce service**, mettez à jour le nom de domaine complet de l’hôte de sorte qu’il pointe vers le pool Lync Server 2013.

5.  Cliquez sur **OK**.

**Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu**

1.  Ouvrez une session sur un ordinateur client du domaine.

2.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

3.  Dans la zone **Ouvrir**, tapez **cmd**, puis cliquez sur **OK**.

4.  À l’invite de commandes, tapez **nslookup** \<nom de domaine complet du\> pool \<frontal ou du nom de domaine\>complet du serveur Standard Edition, puis appuyez sur entrée.

5.  Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.

</div>

<span> </span>

</div>

</div>

</div>

