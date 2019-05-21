---
title: Vérification des rapports de l’administrateur dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Les rapports de l’administrateur contiennent des informations détaillées sur le déploiement et les opérations. Les rapports sont générés à partir des sélections effectuées dans Concevoir des sites. Le concepteur peut compléter les rapports de l’administrateur en modifiant les diagrammes des réseaux et en définissant les adresses IP complètes et les noms de domaine complets (FQDN) pour les serveurs, les pools et les programmes d’équilibrage de charge.
ms.openlocfilehash: 22b3628c5c2a499d57a6bfdd1d90fe3b79b90e85
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288984"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Review the Administrator Reports in Skype for Business Server 2015

Les rapports de l’administrateur contiennent des informations détaillées sur le déploiement et les opérations. Les rapports sont générés à partir des sélections effectuées dans **Concevoir des sites**. Le concepteur peut compléter les rapports de l’administrateur en modifiant les diagrammes des réseaux et en définissant les adresses IP complètes et les noms de domaine complets (FQDN) pour les serveurs, les pools et les programmes d’équilibrage de charge.

La fonctionnalité des rapports Administrateur vous permet d’effectuer les opérations suivantes :

- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)

- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)

- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)

- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Vérifier le rapport récapitulatif
<a name="Summary_report"> </a>

Le rapport d’administration de Skype entreprise est le premier des quatre rapports intéressants qui décrivent en détail votre conception. Les informations de ce rapport, ainsi que celles des trois rapports associés, constituent une documentation utile que pourront exploiter les équipes chargées de l’informatique au sein de votre entreprise :

![Rapport d’administration Synthèse générale](../../media/General_Summary_Report_Admin_Report.png)

Le rapport récapitulatif répertorie des informations de configuration générales relatives à votre réseau de périmètre. Vous y trouverez des informations sur l’emplacement, le nom de domaine complet (FQDN), l’adresse IP, le type de réseau et des commentaires spécifiques à un rôle donné.

Le concepteur ainsi que chacune des équipes chargées de déployer, de gérer et d’assurer la maintenance de l’infrastructure devraient vérifier ce rapport récapitulatif afin de limiter le nombre d’erreurs.

Vous pouvez également afficher plus de rapports détaillés :

- Rapport des certificats

- Rapport du pare-feu

- Rapport DNS

## <a name="review-the-certificates-report"></a>Consulter le rapport de certificats
<a name="Certificates_Report"> </a>

Le rapport certificats contient tous les certificats requis dans le déploiement 2015 de Skype entreprise Server recommandés. Les comptes d’outils de planification pour les noms d’objet et les noms de remplacement d’objet entrés. Le texte par défaut non modifié peut constituer un défi potentiel pour l’équipe qui est responsable de la demande et de l’émission des certificats. Les informations de certificat contiennent également des données sur l’emplacement à partir duquel le certificat peut généralement être émis. Si l’infrastructure ne dispose pas d’une infrastructure à clé publique (PKI) interne, tous les certificats peuvent être demandés par l’intermédiaire d’un fournisseur de certificats public. Les champs Utilisation améliorée de la clé (EKU) et Affecter à du rapport sont très utiles pour comprendre ce que doivent être l’objectif et l’emplacement de chaque certificat.

![Rapport d’administration de certificats](../../media/Certificates_Report_Admin_Report.png)

Examinez et étudiez attentivement l’utilisation et l’objectif de chaque certificat dans le déploiement. En cas de doute sur le rôle d’un certificat, déterminez les éléments avec lesquels le serveur ou le service communique. Les certificats dans Skype entreprise Server 2015 sont utilisés pour deux fonctions principales:

- MTLS (Mutual Transport Layer Security): les ordinateurs impliqués dans la communication présentent chacun un certificat qui révèle leur identité sur un autre ordinateur. On appelle cela l’authentification serveur. La communication ne peut pas commencer tant que chaque ordinateur n’a pas approuvé l’identité de l’autre ordinateur.

- Le chiffrement (Secure Sockets Layer), SSL et TLS (Transport Layer Security) est un moyen essentiel de garantir la sécurité des communications, de garantir la confidentialité et de créer un système de communication et de collaboration approuvé.

## <a name="review-the-firewall-report"></a>Consulter le rapport de pare-feu
<a name="Firewall_report"> </a>

Skype entreprise Server 2015 est doté d’un ensemble de règles de pare-feu potentiellement complexes. L’outil de planification réduit cette complexité en générant un rapport qui définit en détail toutes les exigences de pare-feu, en fonction du critère d’entrée du concepteur. L’administrateur du pare-feu informatique pourra utiliser ce rapport pour configurer et définir les règles nécessaires.

En termes de gestion du pare-feu, le rapport doit être lu attentivement afin de s’assurer qu’il n’y a aucun conflit avec des règles de pare-feu existantes et que toutes les stratégies et procédures sont respectées.

![Rapport d’administration de pare-feu](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Consulter le rapport DNS
<a name="DNS_Report"> </a>

Le rapport DNS, qui fait partie du rapport Administrateur, détaille toutes les entrées recommandées et connues pour le système DNS (Domain Name System) dans les réseaux internes, de périmètre et externes. Si le concepteur a effectué des modifications au diagramme de réseau et que toutes les adresses IP et tous les noms de domaine complets (FQDN) sont définis à leurs valeurs de production, le rapport DNS fournit une excellente ressource de configuration. Ce rapport peut également faire office de document de dépannage opérationnel.

![Rapport d’administration DNS](../../media/DNS_Report_Admin_Report.png)

Votre équipe de gestion DNS doit vérifier le rapport DNS minutieusement, afin de s’assurer qu’il ne contient aucune erreur susceptible de créer des problèmes lors du déploiement ou de compliquer une session de dépannage.

## <a name="see-also"></a>Voir aussi
<a name="DNS_Report"> </a>

[Reviewing the Administrator Reports](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
