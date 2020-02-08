---
title: Liste de contrôle intégration de configuration du réseau pour Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Suivez les tâches principales et les activités de cette liste de vérification lorsque vous configurez votre réseau pour Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97a59ede284474069f39dc166d77d0a4a6ebc167
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862884"
---
# <a name="configure-networking"></a>Configurer la mise en réseau

| Non | Activité ou tâche | Description | Terminé ? | Informations supplémentaires |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Consulter la configuration requise pour Network teams | Bénéficiez d’une vue globale de votre besoin réseau avant d’accéder aux détails du réseau. | | [Préparer le réseau de votre organisation pour Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | Ateliers de préparation du réseau | Effectuer une évaluation de la disponibilité du réseau. | |  |
| 3  | Utiliser le planificateur de réseau | Utiliser la planification de la bande passante réseau. | | |
| 4  | Valider la taille de pool NAT requise pour la connectivité utilisateur | Assurez-vous que les adresses IP publiques appropriées sont affectées aux pools NAT pour empêcher les épuisements de port. L’épuisement du port contribuera aux utilisateurs internes et aux appareils qui ne peuvent pas se connecter au service Office 365. <br/><br/>Les problèmes de connectivité constituent une cause principale de problèmes de perception des utilisateurs pour les services Cloud. | | [Prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | Mettre en œuvre le routage le plus efficace vers les centres de connaissances Microsoft | Identifiez les emplacements qui peuvent utiliser des points de sortie locaux ou régionaux pour vous connecter au réseau Microsoft aussi efficacement que possible. <br/><br/>L’article de la colonne **informations supplémentaires** décrit la façon dont les clients peuvent tirer parti des fonctionnalités de la résolution de noms et du routage IP d’Office 365 pour être connectés efficacement au centre de données régional le plus proche. | | [Connectivité du client Office 365](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | Configurer les ports de pare-feu requis pour la connectivité à teams | Passez en revue les URL et adresses IP pour Office 365 pour identifier et tester les ports de pare-feu requis pour la connectivité entre les clients locaux et les services Office 365. <br/><br/>Pour un environnement pris en charge, vous devez ouvrir tous les ports sur vos pare-feu. Si les problèmes persistent, l’utilisateur ne pourra pas accéder à l’interface utilisateur. Configurez les ports multimédias sur vos pare-feu en fonction des recommandations de la colonne **informations supplémentaires** . | | [URL et adresses IP Office 365-Microsoft teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | Configurer les serveurs proxy | Configurez votre environnement de sorte que les serveurs proxy soient ignorés et que vous puissiez connecter les utilisateurs directement à Office 365 à l’aide du protocole UDP, afin de bénéficier de la meilleure qualité audio et vidéo. Lorsque les contenus multimédias en temps réel sont obligés de traverser un serveur proxy, la pile de médias dans teams est contrainte de basculer sur le protocole TCP, ce qui affecte la qualité de façon négative. <br/><br/>Pour bénéficier d’une meilleure qualité utilisateur, il est préférable de toujours utiliser le protocole UDP. | | [Planification de la gestion et de la qualité des services](https://docs.microsoft.com/MicrosoftTeams/prepare-network) |
| version8  | Configurer le VPN de tunnel scindé | Nous vous recommandons de fournir un autre chemin pour le trafic d’équipes qui ignore le réseau privé virtuel (VPN), connu sous le nom de *réseau privé virtuel (VPN*). Le tunneling fractionné signifie que le trafic pour Office 365 ne traverse pas le VPN mais accède directement à Office 365. Ce changement aura un impact positif sur la qualité, mais aussi l'avantage secondaire de réduire la charge des dispositifs VPN et du réseau de l'organisation. | | Pour implémenter une connexion VPN de tunneling fractionné, contactez votre fournisseur de VPN pour plus d’informations sur la configuration. |
| 09  | Configurer la hiérarchisation des paquets à l’aide de QoS | La QoS doit être implémentée sur tous les segments d’un réseau géré. Même si un réseau a été configuré de manière appropriée pour la bande passante, la fonction QoS fournit une réduction des risques en cas d’événement réseau inattendus. Lorsque la qualité de service (QoS) est implémentée, le trafic vocal est prioritaire de sorte que ces événements inattendus n’affectent pas la qualité. | | [Planification de la gestion et de la qualité des services](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[Qualité de service (QoS) dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 0,10 | Optimiser les réseaux Wi-Fi de qualité et de performance | Plusieurs facteurs entrent en jeu lorsque vous optimisez votre réseau Wi-Fi : <ul><li>Mise en œuvre de la qualité de service (WMM) ou du multimédia Wi-Fi (WMM) pour garantir le classement du trafic multimédia sur les réseaux Wi-Fi.</li><li>Planification et optimisation des bandes Wi-Fi et du placement de points d’accès. La plage de 2,4 GHz peut fournir des performances suffisantes, en fonction du placement du point d’accès.</li></ul> Pour obtenir des instructions spécifiques, contactez votre fournisseur de réseaux Wi-Fi. | | [Recommandations Wi-Fi pour les points de terminaison](https://docs.microsoft.com/MicrosoftTeams/prepare-network#wi-fi-recommendations-for-endpoints) |
| 27,9 | Valider la connectivité réseau à l’aide de l’outil d’évaluation du réseau | Utilisez l’outil d’évaluation de réseau pour Skype entreprise et équipes pour tester la connectivité à toutes les adresses IP et tous les ports utilisés dans Skype entreprise Online ainsi qu’aux appels et réunions Teams. Téléchargez l’outil et consultez utilisation. docx pour plus d’informations sur la façon d’utiliser l’outil et d’interpréter les résultats des tests. Nous vous recommandons d’exécuter l’outil à partir d’un PC client dans chaque emplacement où les équipes seront utilisées. | | [Outil d’évaluation du réseau Skype entreprise et équipes](https://go.microsoft.com/fwlink/?linkid=855799) |
