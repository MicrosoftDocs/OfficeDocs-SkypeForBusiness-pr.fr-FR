---
title: "Pr. en ch. de l’intég. de la mess. unifiée Exchange héb. dans Lync Server 2013"
TOCTitle: Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398821(v=OCS.15)
ms:contentKeyID: 49298824
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

L’application de routage de messagerie unifiée Exchange Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange dans un environnement local, où Lync Server 2013 et la messagerie unifiée Exchange sont installés localement dans votre entreprise, ou l’intégration à la messagerie unifiée Exchange hébergée par un fournisseur de services, comme indiqué dans le diagramme suivant.

![Déploiement UM Lync Server Exchange sur site](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Déploiement UM Lync Server Exchange sur site")

Les modes suivants sont pris en charge :

  - **Mode local**    Lync Server 2013 et messagerie unifiée Exchange sont déployés sur des serveurs locaux dans votre entreprise.

  - **Mode intersite**    Lync Server 2013 est déployé sur des serveurs locaux dans votre entreprise et la messagerie unifiée Exchange est hébergée dans une solution proposée par un fournisseur de services en ligne, comme un centre de données Microsoft Exchange Online.

  - **Mode mixte**   Votre déploiement Lync Server 2013 comporte des boîtes aux lettres d’utilisateur hébergées sur des serveurs locaux exécutant Microsoft Exchange Server dans votre entreprise et des boîtes aux lettres hébergées dans un centre de données de service Exchange hébergé.
    
    > [!NOTE]  
    > Le mode mixte peut tenir lieu de solution de transition au cours de l’évaluation et du transfert progressif des utilisateurs vers la messagerie unifiée Exchange hébergée, ou de solution permanente, si vous décidez de conserver localement les services de messagerie unifiée Exchange de certains utilisateurs après en avoir transférés d’autres.

Pour intégrer Lync Server 2013 à la messagerie unifiée Exchange hébergée, vous devez configurer un *espace d’adressage SIP partagé* (également appelé *domaine fractionné* ). Dans cette configuration, Lync Server 2013 et le fournisseur de services tiers de messagerie unifiée Exchange hébergés peuvent accéder au même espace d’adressage de domaine SIP. Pour plus d’informations, reportez-vous à [Architecture d’intégration de messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) dans la documentation de planification.

