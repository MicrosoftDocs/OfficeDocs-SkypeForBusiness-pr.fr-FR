---
title: Création d’un enregistrement SRV DNS pour l’intégrer à la messagerie unifiée Exchange hébergée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Création d’un enregistrement SRV DNS pour l’intégrer à la messagerie unifiée Exchange hébergée

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Cette rubrique décrit comment configurer l’enregistrement SRV DNS (Domain Name System) requis pour un serveur Edge Lync Server 2013 pour le routage vers un service Exchange hébergé tel que Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Pour créer un enregistrement SRV DNS externe pour le service Exchange hébergé

1.  Connectez-vous au serveur DNS externe en tant que membre du groupe DnsAdmins.

2.  Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, puis sélectionnez le domaine SIP dans lequel Lync Server 2013 sera installé.
    
    <div>
    

    > [!IMPORTANT]
    > Vous devez créer l’enregistrement SRV DNS dans le domaine SIP sur lequel Lync Server est ou sera installé. Lorsque vous créez l’enregistrement SRV, le nom de domaine complet (FQDN) utilisé pour le champ Host qui offre ce service doit être le nom de domaine complet (FQDN) externe du pool Edge. Par exemple, si le nom de domaine complet externe de votre pool Edge est edge01.contoso.net, entrez cette valeur. Cela doit également se trouver dans le même domaine que l’enregistrement DNS hosts (A).

    
    </div>

4.  Cliquez avec le bouton droit sur le domaine sélectionné, puis cliquez sur **nouveaux enregistrements**.

5.  Dans **type d’enregistrement de ressource**, cliquez sur **emplacement du service (SRV)**, puis cliquez sur **créer un enregistrement**.

6.  Dans **nouvel enregistrement de ressource**, cliquez sur **service**, puis tapez ** \_sipfederationtls**.

7.  Cliquez sur **protocole**, puis tapez ** \_TCP**.

8.  Cliquez sur **Numéro de port**, puis saisissez **5061**.

9.  Cliquez sur **hôte proposant ce service**, puis tapez le nom de domaine complet (FQDN) du pool de périphériques lync Server 2013 qui permet d’accéder à votre système lync Server 2013 pour les clients externes approuvés.
    
    <div>
    

    > [!NOTE]
    > Le domaine doit également être configuré en tant que domaine forcé et accepté dans vos paramètres Exchange Online. Pour plus d’informations, consultez créer des <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>domaines approuvés sur.

    
    </div>

10. Cliquez sur **OK**, puis sur **Terminé**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Pour vérifier que l’enregistrement SRV DNS a été correctement créé

1.  Connectez-vous à un ordinateur client dans le domaine.

2.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

3.  À l’invite de commandes, exécutez la commande suivante :
    
        nslookup <FQDN Lync Edge Pool>

4.  Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

