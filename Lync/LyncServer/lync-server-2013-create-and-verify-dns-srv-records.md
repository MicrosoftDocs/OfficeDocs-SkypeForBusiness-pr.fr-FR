---
title: 'Lync Server 2013 : création et vérification des enregistrements SRV DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7faf0cd00b59d5df5bab1650a28eff8b9563f91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Créer et vérifier des enregistrements SRV DNS dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

Cette rubrique décrit comment configurer les enregistrements DNS (Domain Name System) que vous devez créer dans les déploiements de Lync Server 2013 et ceux requis pour la connexion automatique des clients. Lorsque vous créez un pool frontal, le programme d’installation crée des objets et des paramètres Active Directory pour le pool, y compris le nom de domaine complet (FQDN) du pool. Des objets et des paramètres similaires sont créés pour un serveur Standard Edition. Pour que les clients puissent se connecter au pool ou au serveur Standard Edition, le nom de domaine complet (FQDN) du pool ou du serveur Standard Edition doit être enregistré dans le système DNS. Vous devez créer des enregistrements SRV DNS dans votre serveur DNS interne pour chaque domaine SIP. Cela présuppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Pour configurer un enregistrement DNS SRV

1.  Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine SIP dans lequel Lync Server 2013 sera installé.

3.  Cliquez sur **Nouveaux enregistrements**.

4.  Dans **Choisissez un type d’enregistrement de ressource**, cliquez sur **Emplacement du service (SRV)**, puis sur **Créer un enregistrement**.

5.  Cliquez sur **service**, puis tapez ** \_sipinternaltls**.

6.  Cliquez sur **protocole**, puis tapez ** \_TCP**.

7.  Cliquez sur **Numéro de port**, puis tapez **5061**.

8.  Cliquez sur **hôte offrant ce service**, puis tapez le nom de domaine complet (FQDN) du pool ou du serveur Standard Edition.

9.  Cliquez sur **OK**, puis sur **Terminé**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Pour vérifier la création d’un enregistrement DNS SRV

1.  Ouvrez une session sur un ordinateur client du domaine dont le compte est membre du groupe Utilisateurs authentifiés ou qui dispose des autorisations équivalentes.

2.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

3.  Dans la zone **Ouvrir**, tapez **cmd**, puis cliquez sur **OK**.

4.  À l’invite de commandes, tapez **nslookup**, puis appuyez sur Entrée.

5.  Tapez **set type=srv**, puis appuyez sur Entrée.

6.  Tapez ** \_sipinternaltls.\_ tcp.contoso.com**, puis appuyez sur entrée. Le résultat obtenu pour l’enregistrement TLS (Transport Layer Security, sécurité de la couche de transport) est le suivant :
    
    Serveur : \<DNS server\>. contoso.com
    
    Adresse : \<adresse IP du serveur DNS\>
    
    Réponse ne faisant pas autorité :
    
    \_sipinternaltls. \_emplacement du service SRV TCP.contoso.com :
    
    priorité = 0
    
    poids = 0
    
    port = 5061
    
    nom de l’hôte : poolname.contoso.com (ou enregistrement A du serveur Standard Edition)
    
    adresse Internet poolname.contoso.com = \<adresse IP virtuelle de l’équilibreur de\> charge \<ou adresse IP d’un serveur Enterprise Edition unique pour les pools avec un seul\> serveur \<Enterprise Edition ou adresse IP du serveur Standard Edition\>

7.  Lorsque vous avez terminé, à l’invite de commandes, tapez **exit** et appuyez sur Entrée.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu

1.  Ouvrez une session sur un ordinateur client du domaine.

2.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

3.  Dans la zone **Ouvrir**, tapez **cmd**, puis cliquez sur **OK**.

4.  À l’invite de commandes, tapez **nslookup** \<nom de domaine complet du\> pool \<frontal ou du nom de domaine\>complet du serveur Standard Edition, puis appuyez sur entrée.

5.  Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

