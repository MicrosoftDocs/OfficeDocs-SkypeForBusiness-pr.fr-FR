---
title: "Lync Server 2013 : Conf. de la féd. pour un fourn. de serv. d’audioconférence"
TOCTitle: Configuration de la fédération pour un fournisseur de services d’audioconférence
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn510996(v=OCS.15)
ms:contentKeyID: 59954038
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la fédération pour un fournisseur de services d’audioconférence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-07-24_

Si vous souhaitez utiliser un fournisseur de services d’audioconférence (ACP) dans votre déploiement hybride (Lync Server local avec Lync Online), vous devez configurer la fédération entre votre déploiement Lync local et le partenaire ACP en tant que serveur partenaire autorisé. Vous pouvez configurer la fédération en ajoutant le domaine du partenaire ACP et le serveur Edge (également appelé « proxy d’accès ») à la liste des domaines fédérés pour votre déploiement local. Votre partenaire ACP doit ensuite ajouter le nom de domaine complet (FQDN) de votre pool de serveurs Edge local à sa liste de domaines fédérés autorisés. Pour plus d’informations, contactez votre fournisseur ACP.

  - **Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**
    
    Pour ajouter le domaine ACP en tant que serveur du partenaire autorisé (domaine fédéré autorisé), suivez la procédure de la section [Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md). Pour le serveur Edge, ajoutez le nom de domaine complet (FQDN) du serveur Edge du partenaire ACP. Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, que votre ACP peut également appelé « proxy d’accès ».

  - **Transmission du nom de domaine complet (FQDN) de votre pool de serveurs Edge au partenaire ACP**
    
    Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.

