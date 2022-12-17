---
title: Données et informations de confidentialité
author: altsou
ms.author: altsou
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Données et informations de confidentialité
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: dd80718da862be02b42a5cf18334c89e86c3807c
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438425"
---
# <a name="approach"></a>Approche

Les clients qui utilisent Salles Microsoft Teams Services managés Microsoft confient leur ressource la plus précieuse: les données. Ils sont confiants que sa vie privée sera protégée et qu’elle ne sera utilisée que d’une manière conforme à leurs attentes.

La technologie suit les processus de confidentialité pour s’assurer qu’elle respecte les promesses du client lors de la collecte et de l’utilisation des données qui exécutent efficacement le service.
## <a name="data-collection-and-privacy"></a>Collecte et confidentialité des données

 Salles Microsoft Teams Managed Services surveille les appareils, collecte les données de contenu client et accède et gère à distance les appareils en tant qu’administrateur. Les données collectées sont limitées aux informations requises pour surveiller l’intégrité, la cause racine et l’atténuation des problèmes identifiés dans les salles inscrites. Certaines données collectées sont spécifiques à un compte de salle, et non à des utilisateurs individuels.

> [!Note]
> Des références accessoires à un utilisateur individuel peuvent être présentes dans le journal d’activité pendant l’utilisation de l’appareil.

## <a name="who-can-access-data"></a>Qui peut accéder aux données

Managed Services prend des mesures fortes pour protéger les données client contre tout accès ou utilisation inapproprié par des personnes non autorisées. Ces mesures comprennent la restriction de l’accès du personnel Microsoft et des sous-traitants.

## <a name="zero-standing-access-data-storage"></a>Stockage de données Avec accès permanent zéro

Les services managés atténuent les risques associés aux comptes disposant d’un accès privilégié d’acteurs malveillants, à la fois à l’intérieur et à l’extérieur d’une organisation, par le biais du principe de l’accès permanent zéro. Ce principe permet aux services gérés de fonctionner sans aucun privilège disponible pour n’importe quel utilisateur par défaut. Combiné aux principes juste-à-temps et Juste-assez-accès, il fournit un framework robuste pour être sécurisé et conforme par défaut. Les données de diagnostic sont disponibles pour l’équipe des opérations de service Microsoft via un portail interne.

## <a name="data-handling"></a>Gestion des données

Microsoft est régie par des normes strictes en matière de transmission, de stockage, d’utilisation et de conservation des données. Microsoft dispose de stratégies standard de gestion des données qui régissent la façon dont les données doivent être gérées en fonction de la classification des données.

## <a name="technology-description"></a>Description de la technologie

Managed Services envoie des données à Microsoft à des fins de surveillance, de diagnostic et d’atténuation des problèmes liés au déploiement. Exemples :

- Vérifier que l’appareil est à jour (y compris l’application, le système d’exploitation, les pilotes, F/W)
- Vérifier que l’appareil est prêt à être utilisé (connecté, tous les périphériques signalant un état sain, etc.)
- S’assurer que l’environnement est prêt (comptes approvisionnés, vitesses réseau suffisamment rapides, etc.)
- Déterminer s’il peut y avoir des problèmes matériels ou d’installation (par exemple, un câblage souple)
- Heuristique pour déterminer les problèmes (redémarrages excessifs, etc.)

Managed Services gère l’appareil avec les actions suivantes :

- Mettre à jour le logiciel
- Atténuer les problèmes par le biais de redémarrages, de la réinitialisation des connexions USB & états
- Collecter des journaux spécifiques pour faciliter le diagnostic des problèmes

Managed Services ne surveille pas ni n’enregistre le contenu audio, vidéo, multimédia ou de réunion à partir des kits de solutions.

### <a name="service-collected-data-categories"></a>Catégories de données collectées par le service
 
|Catégorie|Détails|Motif de la requête|
| :- | :- | :- |
|Collecte et gestion continues des données|Adresse IP, identité du compte de salle (Exchange, Skype Entreprise et/ou Teams), coordonnées d’emplacement, e-mails et communication dans le portail avec Microsoft ou un logiciel|Identifier et se connecter au système géré ; identifier, diagnostiquer et atténuer les défaillances ; suivre l’utilisation, l’analytique et les insights ; état de la connectivité de requête et de réparation|
|Collecte et gestion des données ad hoc|Informations du journal des événements, activité de l’utilisateur/identité de l’utilisateur de la salle connecté au fichier journal, ainsi que des informations de diagnostic, requêtes système Windows (exemples : liste des périphériques USB, état d’alimentation, etc.)|Identifier, diagnostiquer et atténuer les défaillances et pour l’utilisation, l’analytique et les insights|

Certaines données sensibles dans le journal activité de l’appareil sont expurgées localement (non collectées par Managed Services) :

- Objet et corps de la réunion
- Informations de carte de visite pour les participants à la réunion (par exemple, titre, numéro de téléphone, etc.)
- Contenu du message de messagerie instantanée de réunion

> [!NOTE]
> À mesure que Microsoft évoluent, les données spécifiques sont susceptibles d’être modifiées.

### <a name="enrollment"></a>Inscription

Managed Services est inscrit auprès du portail en ligne pour la surveillance automatisée et les services de support, y compris les diagnostics et les rapports. L’inscription s’effectue via des communications réseau chiffrées à l’aide de la clé publique basée sur le module de plateforme sécurisée (TPM) de l’appareil.

### <a name="unenrollment"></a>Désinscription

L’appareil peut être désinscrit en désinstallant Managed Services. Microsoft supprime également l’appareil de la surveillance du back-end pendant la désaffectation et peut supprimer les données collectées sur demande.
## <a name="compliance"></a>Conformité

Tous les ingénieurs qui travaillent sur le produit doivent suivre une formation de sensibilisation à la sécurité et à la confidentialité. Microsoft s’assure également que tout le personnel certifie l’acceptation des responsabilités en matière d’exigences en matière de confidentialité.

Managed Services prend en charge la résidence des données régionales via les centres de données en Europe (UE), en Asie-Pacifique (APAC) et en États-Unis (États-Unis). Les clients du service auront des données relatives à l’organisation stockées dans le centre de données de la région choisie.

## <a name="more-resources"></a>Autres ressources

Salles Microsoft Teams sur la sécurité Windows : [[Microsoft Teams pour la sécurité Windows](/microsoftteams/rooms/security-windows) \
Salles Microsoft Teams sur la sécurité Android : [Microsoft Teams pour la sécurité Android](/microsoftteams/rooms/security-android) \
Microsoft déclaration de confidentialité :https://aka.ms/privacy \
Gestion des données au Microsoft :https://www.microsoft.com/trust-center/privacy/data-management \
Description du service Services managés : [Microsoft Service géré par salle Teams](rooms-pro-management.md)
