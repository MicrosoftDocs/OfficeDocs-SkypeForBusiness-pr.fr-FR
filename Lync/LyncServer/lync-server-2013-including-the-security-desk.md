---
title: 'Lync Server 2013 : Intégration du service de sécurité'
TOCTitle: Intégration du service de sécurité
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398299(v=OCS.15)
ms:contentKeyID: 49297122
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Intégration du service de sécurité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-02_

Votre entreprise est susceptible de demander au service de sécurité de prendre part au traitement d’un appel d’urgence. Pour vous aider à décider comment intégrer le service de sécurité dans votre déploiement E9-1-1, répondez aux questions suivantes.

  - **Souhaitez-vous que le service de sécurité soit averti en cas d’appel d’urgence ?**  
    Vous pouvez configurer la stratégie d’emplacement afin que Lync Server envoie des alertes par messagerie instantanée aux adresses SIP Lync d’une ou de plusieurs personnes du personnel de sécurité. Ces alertes contiennent le nom, le numéro et l’emplacement de la personne qui a passé l’appel d’urgence. En outre, elles facilitent l’intervention du personnel de sécurité en cas de situation d’urgence.

<!-- end list -->

  - **Souhaitez-vous établir une conférence avec le service de sécurité pour chaque appel d’urgence ?**  
    Si elle est prise en charge par le fournisseur de services d’urgence, vous pouvez configurer la stratégie d’emplacement pour inclure un numéro de rappel à chaque appel d’urgence. Ce numéro est alors utilisé par le fournisseur pour établir une conférence avec le personnel de sécurité de votre organisation pour les appels d’urgence. Cette conférence peut être configurée dans la stratégie d’emplacement en mode unidirectionnel (écoute uniquement) ou bidirectionnel.

> [!NOTE]  
> Si nécessaire, vous pouvez définir des membres du personnel différents pour chaque stratégie d’emplacement. Vous pouvez ainsi personnaliser la réponse en fonction des différents secteurs de votre entreprise ou créer un comportement spécifique pour les appels d’urgence passés dans le réseau et non en dehors du réseau. Vous pouvez utiliser des groupes de distribution pour spécifier le personnel à avertir.
