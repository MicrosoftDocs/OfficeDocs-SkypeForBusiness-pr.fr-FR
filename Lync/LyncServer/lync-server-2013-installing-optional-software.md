---
title: 'Lync Server 2013 : Installation de logiciels facultatifs'
TOCTitle: Installation de logiciels facultatifs
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615032(v=OCS.15)
ms:contentKeyID: 53095509
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation de logiciels facultatifs dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

L’outil de planification Microsoft Lync Server 2013 est conçu pour exporter des éléments vers Microsoft Excel, Microsoft Visio. Même si ces applications ne sont pas nécessaires pour le fonctionnement de l’outil de planification, elles ajoutent une valeur significative au déploiement et à la documentation de votre conception.

## Logiciels facultatifs

## Microsoft Excel

L’exportation de votre conception vers Microsoft Excel permet de créer un rapport sous forme de feuille de calcul à quatre onglets :

  - Synthèse : affiche des informations sur la configuration du site, notamment le nombre d’utilisateurs, les paramètres de capacité et les informations de profil du serveur.

  - Profil matériel : affiche un rapport détaillant les configurations matérielles recommandées pour les serveurs spécifiés dans la topologie, y compris le processeur, la mémoire, le disque et l’interface réseau. La quantité et les caractéristiques conseillées pour les composants serveur y figurent également. Par ailleurs, chaque serveur est défini par site afin de fournir une représentation complète de la configuration serveur requise pour chaque site.

  - Configuration requise pour les ports : affiche un rapport de tous les ports activés et l’association entre l’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle. Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations de l’équilibrage de la charge DNS et des programmes d’équilibrage de la charge matérielle.

  - Rapport de synthèse : affiche la synthèse générale des paramètres requis pour configurer votre réseau serveur Edge.

  - Rapport de certificats : affiche le nom du sujet et les autres noms du sujet requis pour les certificats nécessaires au fonctionnement des serveurs Edge.

  - Rapport de pare-feu : affiche les adresses IP et ports sources et de destination des interfaces internes et externes.

  - Rapport DNS : affiche le nom de domaine complet et les adresses IP/VIP requises pour chaque entrée DNS que vous créez.

## Microsoft Visio

L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :

> [!NOTE]  
> Si votre conception est d’une taille suffisamment importante et nécessite plus de trois serveurs frontaux, une page supplémentaire est créée pour le pool de serveurs frontaux, les serveurs frontaux, l’ordinateur SQL Server, les adresses IP et les noms de domaine complets.

  - Topologie globale : diagramme des sites Lync Server 2013 configurés.

  - Onglet Nom du site : affiche la topologie de configuration du site avec serveur Edge, le pare-feu, le réseau téléphonique commuté (RTC) avec les passerelles et le déploiement de serveur interne. Le déploiement interne se compose de serveurs et de pools configurés, y compris les pools frontaux, les serveurs SQL Server, les services de domaine Active Directory, les directeurs, les serveurs de messagerie unifiée Exchange, les serveurs de boîtes aux lettres Exchange, les serveurs Office Web Apps, les serveurs de médiation et les serveurs de conversations permanentes.

  - Diagramme du réseau de périmètre : diagramme détaillant la configuration du serveur Edge avec les adresses IP associées et les noms de domaine complets. L’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus. De plus, les directeurs et le serveur frontal ou le pool de serveurs frontaux sont affichés avec l’équilibrage de la charge DNS ou les programmes d’équilibrage de la charge matérielle associés, ainsi que l’adresse IP (l’outil outil de planification prend en charge les adresses IPv4 et IPv6) et le nom de domaine complet affectés.

## Voir aussi

#### Tâches

[Installation de l’outil de planification dans Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)

