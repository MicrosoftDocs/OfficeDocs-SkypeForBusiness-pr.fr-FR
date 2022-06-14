---
title: Données et informations de confidentialité
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Données et informations de confidentialité
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 3fa24a1009c5480c308dfc35306286d470178820
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057084"
---
# <a name="approach"></a>Approche

Les clients qui utilisent Salles Microsoft Teams Services managés confient à Microsoft leur ressource la plus précieuse : les données. Ils espèrent que sa vie privée sera protégée et qu’elle ne sera utilisée que d’une manière conforme à leurs attentes.

La technologie suit les processus de confidentialité pour s’assurer qu’elle respecte les promesses du client en matière de collecte et d’utilisation des données exécutant efficacement le service.
## <a name="data-collection-and-privacy"></a>Collecte et confidentialité des données

 Salles Microsoft Teams Managed Services surveille les appareils, collecte les données de contenu client, accède à distance et gère les appareils en tant qu’administrateur. Les données collectées sont limitées aux informations requises pour surveiller l’intégrité, la cause racine et l’atténuation des problèmes identifiés dans les salles inscrites. Certaines données collectées sont spécifiques à un compte de salle, et non à des utilisateurs individuels.

> [!Note]
> Des références incidentes à un utilisateur individuel peuvent être présentes dans le journal d’activité lors de l’utilisation de l’appareil.

## <a name="who-can-access-data"></a>Qui pouvez accéder aux données

Managed Services prend des mesures fortes pour protéger les données client contre un accès inapproprié ou une utilisation inappropriée par des personnes non autorisées. Ces mesures incluent la restriction de l’accès par le personnel et les sous-traitants de Microsoft.

## <a name="zero-standing-access-data-storage"></a>Stockage de données à accès permanent zéro

Managed Services atténue les risques associés aux comptes disposant d’un accès privilégié à partir d’acteurs malveillants, tant à l’intérieur qu’à l’extérieur d’une organisation, par le biais du principe de l’accès permanent zéro. Ce principe permet aux services managés de fonctionner sans privilèges disponibles par défaut pour n’importe quel utilisateur. Combinée aux principes de Just-In-Time et Just-Enough-Access, elle fournit une infrastructure robuste pour être sécurisée et conforme par défaut. Les données de diagnostic sont disponibles pour l’équipe des opérations du service Microsoft via un portail interne.

## <a name="data-handling"></a>Gestion des données

Microsoft est régi par des normes strictes pour la transmission, le stockage, l’utilisation et la rétention des données. Microsoft dispose de stratégies standard de gestion des données qui réglementent la façon dont les données doivent être gérées en fonction de la classification des données.



## <a name="technology-description"></a>Description de la technologie

Managed Services envoie des données à Microsoft à des fins de surveillance, de diagnostic et d’atténuation des problèmes dans le déploiement. Exemples :

- S’assurer que l’appareil est à jour (y compris l’application, le système d’exploitation, les pilotes, F/W)
- S’assurer que l’appareil est prêt à être utilisé (connecté, tous les périphériques signalant un état sain, etc.)
- S’assurer que l’environnement est prêt (comptes approvisionnés, vitesse réseau suffisamment rapide, etc.)
- Déterminer s’il peut y avoir des problèmes matériels ou des problèmes d’installation (par exemple, un câblage libre)
- Heuristique pour déterminer les problèmes (redémarrages excessifs, etc.)

Managed Services gère l’appareil avec les actions suivantes :

- Mettre à jour le logiciel
- Atténuer les problèmes par le biais de redémarrages, de la réinitialisation des connexions USB & états
- Collecter des journaux spécifiques pour aider à diagnostiquer les problèmes

Managed Services ne surveille pas ou n’enregistre pas le contenu audio, vidéo, multimédia ou de réunion à partir de kits de solutions.

### <a name="service-collected-data-categories"></a>Catégories de données collectées par le service
 
|Catégorie|Détails|Motif de la requête|
| :- | :- | :- |
|Collecte et gestion des données en cours|Adresse IP, identité du compte de salle (Exchange, Skype Entreprise et/ou Teams), coordonnées d’emplacement, e-mails et communication dans le portail avec Microsoft ou logiciel|Identifier et se connecter au système sous gestion ; identifier, diagnostiquer et atténuer les défaillances ; suivre l’utilisation, l’analytique et les insights ; interroger et réparer l’état de connectivité|
|Collecte et gestion de données ad hoc|Informations sur le journal des événements, l’activité utilisateur/l’identité de l’utilisateur de la salle connectée au fichier journal, ainsi que les informations de diagnostic, Windows requêtes système (exemples : liste des périphériques USB, état de l’alimentation, etc.)|Identifier, diagnostiquer et atténuer les échecs et pour l’utilisation, l’analytique et les insights|

Certaines données sensibles dans le journal d’activité de l’appareil sont expurgées localement (non collectées par Managed Services) :

- Objet et corps de la réunion
- Informations de carte de visite pour les participants à la réunion (par exemple, titre, numéro de téléphone, etc.)
- Dans le contenu du message instantané de réunion

> [!NOTE]
> À mesure que Microsoft évolue dans les services managés, les données spécifiques sont susceptibles de changer.

### <a name="enrollment"></a>Inscription

Managed Services est inscrit auprès du portail en ligne pour les services de supervision et de support automatisés, notamment les diagnostics et les rapports. L’inscription s’effectue via des communications réseau chiffrées à l’aide de la clé publique basée sur le module de plateforme sécurisée (TPM) de l’appareil.

### <a name="unenrollment"></a>Désinscription

L’appareil peut être désinscrit en désinstallant Managed Services. Microsoft supprime également l’appareil de la surveillance du serveur principal pendant la mise hors service et peut supprimer les données collectées sur demande.
## <a name="compliance"></a>Conformité

Tous les ingénieurs qui travaillent sur le produit doivent suivre une formation sur la sécurité et la confidentialité. Microsoft garantit également que tout le personnel certifie l’acceptation des responsabilités en matière de confidentialité.

Managed Services fournit une prise en charge régionale de la résidence des données par le biais des centres de données en Europe (UE), Asie-Pacifique (APAC) et États-Unis (États-Unis). Les clients du service auront des données relatives à l’organisation stockées dans le centre de données de la région choisie.

## <a name="more-resources"></a>Plus de ressources

Salles Microsoft Teams Security:/microsoftteams/rooms/security Microsoft Privacy Statement : https://aka.ms/privacy Gestion des données chez Microsoft : https://www.microsoft.com/trust-center/privacy/data-management Description du service Services managés : [Microsoft Teams service managé room](microsoft-teams-rooms-premium.md)
