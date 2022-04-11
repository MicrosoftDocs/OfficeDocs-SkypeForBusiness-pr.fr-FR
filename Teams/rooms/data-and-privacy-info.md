---
title: Données et informations de confidentialité
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
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
ms.openlocfilehash: 0aea2402705eb817c7f075cf003245c0ad3258fd
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/11/2022
ms.locfileid: "64757117"
---
# <a name="approach"></a>Approche

Les clients qui utilisent des services managés confient à Microsoft leur ressource la plus précieuse : les données. Ils espèrent que sa vie privée sera protégée et qu’elle ne sera utilisée que d’une manière conforme à leurs attentes.

La technologie suit les processus de confidentialité pour s’assurer qu’elle respecte les promesses des clients lors de la collecte et de l’utilisation des données en exécutant le service de manière efficace.

## <a name="data-collection"></a>Collecte de données

Les données collectées par la technologie sont limitées aux informations requises pour surveiller l’intégrité, la cause racine et atténuer les problèmes identifiés dans les salles inscrites.

La technologie surveille les appareils, collecte les données de télémétrie et permet à Microsoft d’accéder et de gérer les appareils à distance en tant qu’administrateur.

Les données de télémétrie collectées sont spécifiques à un compte Room, et non à un utilisateur individuel. Des références incidentes à un utilisateur individuel peuvent être présentes dans le journal d’activité lors de l’utilisation de l’appareil.

### <a name="who-can-access-your-data"></a>Qui pouvez accéder à vos données

Le service Technologie prend des mesures fortes pour protéger les données client contre un accès inapproprié ou une utilisation inappropriée par des personnes non autorisées. Cela inclut la restriction de l’accès par le personnel et les sous-traitants de Microsoft.

### <a name="zero-standing-access-data-storage"></a>Stockage de données d’accès permanent zéro

La technologie atténue les risques associés aux comptes disposant d’un accès privilégié ( des acteurs malveillants à l’intérieur et à l’extérieur d’une organisation ) par le biais du principe de l’accès permanent zéro. Cela permet au service de fonctionner sans privilèges disponibles par défaut pour n’importe quel utilisateur. Combinée aux principes de Just-In-Time et Just-Enough-Access, elle fournit une infrastructure robuste pour être sécurisée et conforme par défaut. Les données de diagnostic sont disponibles pour notre équipe des opérations de service via un portail interne.

## <a name="data-handling"></a>Gestion des données

Microsoft est régi par des normes strictes pour la transmission, le stockage, l’utilisation et la rétention des données. Microsoft a des stratégies standard de gestion des données qui permettent de gérer les données en fonction de la classification des données.

Microsoft étend les droits de protection des données du Règlement général sur la protection des données (RGPD) à tous les clients du monde entier, pas seulement en Europe.

## <a name="data-classification"></a>Classification des données

La classification des données peut être utilisée pour respecter les exigences de sécurité, de conformité et de confidentialité et les processus de collecte, de stockage et d’utilisation des informations personnelles de l’utilisateur.


|Classification|Description|Exemple|
| :- | :- | :- |
|Contenu client|Contenu directement fourni/créé par les administrateurs et les utilisateurs.|<p>- Données blob générées par le client ou de stockage structuré</p><p>- Secrets appartenant au client/fournis (mots de passe, certificats, clés de chiffrement, clés de stockage)</p>|
|Informations d’identification de l’utilisateur final (EUII)|Données qui identifient ou peuvent être utilisées pour identifier l’utilisateur d’un service Microsoft. EUII ne contient pas de contenu client.|<p>- Nom d’utilisateur ou nom d’affichage (DOMAIN\UserName)</p><p>- Nom d’utilisateur principal (name@company.com)</p><p>- Adresse IP spécifique à l’utilisateur</p>|
|Données de compte|<p>Informations de facturation client et informations sur l’instrument de paiement, y compris les informations de contact de l’administrateur, telles que le locataire</p><p>nom, adresse ou</p><p>numéro de téléphone.</p>|<p>- Informations de contact de l’administrateur client (par exemple,</p><p>nom, adresse, adresse de messagerie, numéro de téléphone de l’administrateur client)</p><p>- Provisionnement du client</p><p>Informations</p>|
|Identificateurs pseudonymes de l’utilisateur final (EUPI)|<p>Identificateur créé par Microsoft lié à l’utilisateur d’un service Microsoft. Quand l’EUPI est combiné à d’autres informations, telles qu’une table de mappage, il identifie l’utilisateur final. L’EUPI ne contient pas d’informations chargées ou créées par le client</p><p>(Contenu client ou EUII)</p>|<p>- GUID utilisateur, PUIDs ou SID</p><p>- ID de session</p>|
|Informations d’identification de l’organisation (OII)|Données qui peuvent être utilisées pour identifier un locataire, généralement des données de configuration ou d’utilisation. Ces données ne peuvent pas être liées à un utilisateur et ne contiennent pas de contenu client.|<p>- ID de locataire (non GUID)</p><p>- Nom de domaine dans l’adresse de messagerie (xxx@contoso.com) ou un autre domaine spécifique au locataire</p><p>Informations</p>|
|Métadonnées système|Données générées lors de l’exécution du service ou du programme qui ne sont pas lier à un utilisateur ou à un locataire.|<p>- Journaux des événements</p><p>- Données d’utilisation</p><p>- Données de configuration</p>|

Description de la technologie

La technologie envoie des données à Microsoft à des fins de surveillance, de diagnostic et d’atténuation des problèmes dans le déploiement. Exemples :

1. S’assurer que l’appareil est à jour (y compris l’application, le système d’exploitation, les pilotes, F/W)
1. S’assurer que l’appareil est prêt à être utilisé (connecté, tous les périphériques signalant un état sain, etc.)
1. S’assurer que l’environnement est prêt (comptes approvisionnés, vitesse du réseau suffisamment rapide, etc.)
1. Déterminer s’il peut y avoir des problèmes matériels ou des problèmes d’installation (par exemple, un câblage libre)
1. Heuristique pour déterminer les problèmes (redémarrages excessifs, etc.) 

La technologie gère l’appareil avec des actions telles que

1. Mettre à jour le logiciel
1. Atténuer les problèmes par le biais de redémarrages, de la réinitialisation des connexions USB & états
1. Collecter des journaux spécifiques pour aider à diagnostiquer les problèmes

La technologie ne surveille pas ou n’enregistre pas le contenu audio, vidéo, multimédia ou de réunion à partir de Kits de solutions. 

### <a name="service-collected-data-categories"></a>Catégories de données collectées par le service
 
|Catégorie|Détails|Motif de la requête|
| :- | :- | :- |
|Gestion des & de collecte de données en cours|Adresse IP, identité du compte de salle (Exchange, Skype for Business et/ou Teams), coordonnées d’emplacement, e-mails et communication dans le portail avec Microsoft ou logiciel|Identifier et Connecter au système sous gestion ; Identifier, diagnostiquer et atténuer les échecs ; Suivre l’utilisation, l’analytique et les Informations ; Interroger & réparer l’état de connectivité|
|Gestion des & de collecte de données ad hoc|<p>Informations sur le journal des événements, activité utilisateur/identité de l’utilisateur room connecté au fichier journal, ainsi que les informations\* de diagnostic, Windows requêtes système (exemples : liste d’appareils USB,</p><p>état d’alimentation, etc.)</p>|Identifier, diagnostiquer et atténuer les défaillances et pour l’utilisation, l’analytique et Informations|
|<p>Inscription à la version d’évaluation et</p><p>Installation</p>|<p>requêtes système Windows</p><p>Exemples : Liste des périphériques USB, état de l’alimentation, etc.</p>|<p>Requis pour l’inscription, l’intégration, la commande et la remise,</p><p>et le programme d’installation pour la version d’évaluation.</p>|

\* Les piI sensibles dans le journal d’activité des appareils sont supprimés localement (non collectés par la technologie) :

1. Objet de la réunion & corps
1. Informations de carte de visite pour les participants à la réunion (par exemple, titre, numéro Téléphone, etc.)
1. Contenu du message instantané de réunion

>> [!NOTE]
>À mesure que Microsoft fait évoluer la technologie, les données spécifiques sont susceptibles de changer. 

### <a name="agent-data-classification"></a>Classification des données de l’agent

**Description détaillée de toutes les données collectées par l’agent MTRP pendant la surveillance en cours**
|Description des données collectées|Classification|
| :- | :- |
|Identité d’un appareil partagé|OII|
|ID client|OII|
|Emplacement du répertoire de l’agent MMR|Métadonnées système|
|Emplacement du répertoire des journaux d’application MTR|Métadonnées système|
|Numéro de série de l’appareil|Métadonnées système|
|Informations sur le bios de l’appareil|Métadonnées système|

|Version de l’agent MMR|Métadonnées système|
| :- | :- |
|Version de l’application MTR|Métadonnées système|
|Version de l’application Teams|Métadonnées système|
|Heure du travail de maintenance nocturne pour l’application MTR|Métadonnées système|
|URL de mise à jour de l’agent MMR|Métadonnées système|
|Anneau de l’agent MMR|Métadonnées système|
|Windows version du système d’exploitation|Métadonnées système|
|Utilisateur actuellement connecté|Métadonnées système|
|GUID de session de l’Agent MMR|Métadonnées système|
|Nom du domaine|Métadonnées système|
|Temps écoulé depuis le dernier redémarrage du système d’exploitation|Métadonnées système|
|Heure depuis le dernier démarrage de l’agent MMR|Métadonnées système|
|Modèle et make d’appareil MTR|Métadonnées système|
|État d’utilisation de l’appareil|Métadonnées système|
|Type d’intégration d’appareil|Métadonnées système|
|Nombre de moniteurs connectés|Métadonnées système|
|Détails de l’orateur MTR|Métadonnées système|
|Détails du microphone MTR|Métadonnées système|
|Détails de l’orateur par défaut MTR|Métadonnées système|
|Paramètre de partage d’écran automatique de l’application MTR|Métadonnées système|
|Paramètre de publication de Bluetooth d’application MTR|Métadonnées système|
|Date de la dernière modification du mot de passe|Métadonnées système|
|Paramètre de rotation du mot de passe MTR|Métadonnées système|
|Paramètre Teams/Skype for Business de l’application MTR|Métadonnées système|
|Anneau de mise à jour de l’application MTR|Métadonnées système|
|Paramètre de caméra de contenu de l’application MTR|Métadonnées système|
|Paramètre des noms des réunions d’application MTR|Métadonnées système|
|Paramètre d’affichage de l’application MTR devant la salle|Métadonnées système|
|GUID de l’application MTR|Métadonnées système|
|Adresse proxy et port|Métadonnées système|
|Intégrité de l’appareil MTR|Métadonnées système|
|Détails du compte de salle MTR|OII|
|Adresse IPV4 et adresse IPV6|OII|
|Longitude et latitude|OII|
|Nom d’hôte de l’appareil MTR|OII|
|Fuseau horaire de l’appareil MTR|Métadonnées système|
|État de l’application MTR|Métadonnées système|
|Détails du service Crestron|Métadonnées système|
|Version du microprogramme Logitech et version de synchronisation Logitech|Métadonnées système|
|Pourcentage total d’UC utilisé|Métadonnées système|
|Nombre total de RAM utilisées|Métadonnées système|
|Processeur utilisé par MTR Skype ou Teams Apps|Métadonnées système|
|Température de l’appareil MTR|Métadonnées système|
|État des lecteurs de disque internes|Métadonnées système|
|Détails des blocages d’une application MTR|Métadonnées système|
|Détails des fuites de mémoire détectées causées par les applications sur l’appareil|Métadonnées système|

|<p>Détails des erreurs d’écran bleu de l’appareil qui ont eu lieu sur le</p><p>dernières 24 heures</p>|Métadonnées système|
| :- | :- |
|<p>Détails des erreurs détectées par l’application MTR pendant les réunions sur</p><p>l’appareil</p>|Métadonnées système|
|Détails du logiciel installé|Métadonnées système|
|Détails des correctifs à chaud installés/ en attente/manquants|Métadonnées système|
|Détails du matériel reconnu|Métadonnées système|
|Détails de tous les pilotes sur l’appareil|Métadonnées système|
|Détails des corrections d’appareils MMR|Métadonnées système|
|Détails de l’utilisation de la salle au cours des dernières 24 heures, heure et nombre de réunions|Métadonnées système|
|Détails des mises à jour automatiques du magasin de Windows|Métadonnées système|
|Détails des mises à jour du système d’exploitation Windows|Métadonnées système|
|Détails de l’écrasement de l’agent MMR|Métadonnées système|
|Détails de l’erreur de connexion de l’agent MMR|Métadonnées système|
|Détails sur l’activation de la sécurité TPM|Métadonnées système|
|Détails de l’état de connexion de l’appareil MTR|Métadonnées système|

**Collecte de l’agent MTRP de données pour le diagnostic et la correction des incidents**
|Description des données collectées|Classification|
| :- | :- |
|<p>Journaux des événements : Système, Application, système de salle Skype, Microsoft- Windows-AppXDeploymentServer%4Operational, Microsoft-Windows- PowerShell%4Operational, Microsoft-Windows- AppXDeployment%4Operational,Microsoft-Windows- AppXDeploymentServer%4Operational, Microsoft-Windows - TWinUI%4Operational, Microsoft Managed Rooms, Microsoft-Windows-</p><p>TaskScheduler%4Operational, Security</p>|Métadonnées système|
|Journaux d’activité d’application MTR expurgés\*|Métadonnées système|
|Journaux d’activité des équipes Microsoft|Métadonnées système|
|Agent MMR sqlLitedb|Métadonnées système|
|Détails des informations sur l’état de l’alimentation de l’appareil|Métadonnées système|
|Informations de stratégie de groupe d’appareils|Métadonnées système|
|Auditer la trace de toutes les actions de l’agent MMR|Métadonnées système|
\* Les informations personnelles sensibles dans le journal d’activité des appareils sont rédigées localement.

### <a name="enrollment"></a>Inscription


Cette technologie sera inscrite auprès du portail en ligne pour les services de supervision et de support automatisés, notamment les diagnostics et les rapports. L’inscription s’effectue via des communications réseau chiffrées à l’aide de la clé publique basée sur le module de plateforme sécurisée (TPM) de l’appareil.

### <a name="un-enrollment"></a>Annulation de l’inscription

L’appareil peut être désinscriré en désinstallant la technologie. Microsoft supprimera également l’appareil de la surveillance du serveur principal pendant la mise hors service et pourra supprimer les données collectées sur demande.

### <a name="data-flow"></a>Flux de données

La technologie ajoute un flux de données de l’agent à MTR Managed Services.

![flux de données de l’agent vers MTR Managed Services](../media/data-and-privacy-info-005.png)

L’activation de l’intégration de Pertahanan Microsoft untuk Titik Akhir introduit un flux de données supplémentaire de l’agent MDE vers l’infrastructure Microsoft Defender.

![flux de données supplémentaires de l’agent MDE vers Defender](../media/data-and-privacy-info-006.png)

## <a name="compliance"></a>Conformité

Tous les ingénieurs qui travaillent sur le produit doivent suivre une formation sur la sécurité et la confidentialité. Microsoft garantit également que tout le personnel certifie l’acceptation des responsabilités en matière de confidentialité.

La technologie fournit un support régional de résidence des données par le biais des centres de données en Europe (UE), Asie-Pacifique (APAC) et le États-Unis (États-Unis). Cela signifie que les clients du service auront des données liées à l’organisation stockées dans le centre de données de la région choisie.

## <a name="additional-resources"></a>Ressources supplémentaires

Salles Microsoft Teams Security:/microsoftteams/rooms/security Microsoft Privacy Statement : https://aka.ms/privacy Gestion des données chez Microsoft : https://www.microsoft.com/trust-center/privacy/data-management Description du service de technologie : [Microsoft Teams service managé room](microsoft-teams-rooms-premium.md)
