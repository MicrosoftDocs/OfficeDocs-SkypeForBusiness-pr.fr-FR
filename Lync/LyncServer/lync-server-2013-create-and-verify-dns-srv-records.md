---
title: 'Lync Server 2013 : Création et vérification des enregistrements SRV DNS'
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
ms.openlocfilehash: 8440d2ae91d535c8c4747c923b1b17dda9bb0f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Création et vérification des enregistrements SRV DNS dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe administrateurs de domaine ou membre du groupe DnsAdmins.

Cette rubrique décrit comment configurer les enregistrements DNS (Domain Name System) nécessaires à la création dans les déploiements Lync Server 2013 et ceux requis pour la connexion automatique du client. Lorsque vous créez un pool frontal, le programme d’installation crée des objets et des paramètres Active Directory pour le pool, y compris le nom de domaine complet (FQDN) du pool. Des objets et des paramètres similaires sont créés pour un serveur Standard Edition Server. Pour que les clients puissent se connecter au pool ou Standard Edition Server, le nom de domaine complet (FQDN) du pool ou du serveur Standard Edition doit être enregistré dans DNS. Vous devez créer des enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP. Cette procédure part du principe que votre DNS interne comporte des zones pour vos domaines d’utilisateur SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Pour configurer un enregistrement SRV DNS

1.  Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine SIP sur lequel Lync Server 2013 sera installé.

3.  Cliquez sur **nouveaux enregistrements**.

4.  Dans **Choisissez un type d’enregistrement de ressource**, cliquez sur **Emplacement du service (SRV)**, puis sur **Créer un enregistrement**.

5.  Cliquez sur **service**, puis tapez ** \_sipinternaltls**.

6.  Cliquez sur **protocole**, puis tapez ** \_TCP**.

7.  Cliquez sur **Numéro de port**, puis saisissez **5061**.

8.  Cliquez sur **Hôte offrant ce service**, puis tapez le nom de domaine complet du pool ou du serveur en édition Standard.

9.  Cliquez sur **OK**, puis sur **Terminé**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Pour vérifier la création d’un enregistrement SRV DNS

1.  Ouvrez une session sur un ordinateur client du domaine dont le compte est membre du groupe Utilisateurs authentifiés ou qui dispose des autorisations équivalentes.

2.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

3.  Dans la zone **ouvrir** , tapez **cmd**, puis cliquez sur **OK**.

4.  À l’invite de commandes, tapez **nslookup**, puis appuyez sur entrée.

5.  Tapez **Set type = SRV**, puis appuyez sur entrée.

6.  Tapez ** \_sipinternaltls.\_ tcp.contoso.com**, puis appuyez sur entrée. Le résultat affiché pour l’enregistrement TLS (Transport Layer Security) est le suivant :
    
    Serveur : \<DNS server\>. contoso.com
    
    Adresse : \<adresse IP du serveur DNS\>
    
    Réponse ne faisant pas autorité :
    
    \_sipinternaltls. \_emplacement du service SRV TCP.contoso.com :
    
    Priority = 0
    
    épaisseur = 0
    
    port = 5061
    
    SVR nom d’hôte = poolname.contoso.com (ou enregistrement d’un serveur Standard Edition)
    
    poolname.contoso.com adresse Internet = \<adresse IP virtuelle de l’équilibrage de charge\> ou \<de l’adresse IP d’un serveur Enterprise Edition pour les pools avec un seul\> serveur \<Enterprise Edition ou une adresse IP du serveur Standard Edition Server\>

7.  Lorsque vous avez terminé, à l’invite de commandes, tapez **Exit**, puis appuyez sur entrée.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Pour vérifier que le nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition peut être résolu

1.  Connectez-vous à un ordinateur client dans le domaine.

2.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

3.  Dans la zone **ouvrir** , tapez **cmd**, puis cliquez sur **OK**.

4.  À l’invite de commandes, tapez **nslookup** \<FQDN du pool\> frontal ou \<du FQDN du serveur\>Standard Edition, puis appuyez sur entrée.

5.  Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).

</div>

</div>

<span> </span>

</div>

</div>

</div>

