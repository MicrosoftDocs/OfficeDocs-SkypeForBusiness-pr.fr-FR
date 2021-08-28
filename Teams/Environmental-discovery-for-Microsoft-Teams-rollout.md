---
title: Compatibilité de l’environnement - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Comment effectuer une découverte détaillée de l’environnement lorsque vous planifiez votre voyage de Skype Entreprise à Microsoft Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fdaafeb9042f8b76b40c797109740af5c93ef077
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635048"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Découverte de l’environnement pour un déploiement Microsoft Teams environnement

La découverte est l’une des premières étapes clés que vous devez suivre lorsque vous planifiez votre parcours vers Microsoft Teams.

Vous effectuez une découverte détaillée de votre environnement pour mieux comprendre son état actuel et pour révéler les difficultés ou, encore plus loin, les bloqueurs possibles de l’exécution de votre déploiement Teams.

## <a name="discovery-questionnaire"></a>Questionnaire de découverte

L’exemple de questionnaire ci-dessous vous aide à vérifier que votre organisation est prête à déployer efficacement l’audioconférence et la Système téléphonique avec les fonctionnalités de Plans d’appel dans Teams.

Toutes les questions relatives à votre infrastructure de collaboration existante et à votre organisation Microsoft 365 ou Office 365, à la mise en réseau, aux points de terminaison, aux opérations, à l’adoption et à la préparation sont incluses dans le questionnaire de découverte de l’environnement.

Le questionnaire est divisé en plusieurs sections pour confirmer que votre organisation est prête pour votre déploiement Teams dans plusieurs domaines principaux. Travaillez avec votre équipe de projet pour fournir les informations demandées avec autant de détails que possible afin de faciliter vos activités de planification.

> [!TIP]
> Vous pouvez commencer par copier le questionnaire dans un Microsoft Word document. Essayez de répondre à toutes les questions et capturez tous les détails à mesure que vous vous déplacez.

### <a name="project-team"></a>Project d’équipe

Capturez des informations détaillées sur les principales parties prenantes de Teams projet de déploiement. Notez qu’une seule personne peut jouer plusieurs rôles tout au long du projet.

> | Rôle | Nom, adresse e-mail, numéro de téléphone | Emplacement, fuseau horaire | Commentaires |
> |---|---|---|---|
> | Sponsor exécutif | | | |
> | Chef de projet | | | |
> | Chef/architecte de la collaboration | | | |
> | Consultant | | | |
> | Gestionnaire de projets | | | |
> | Spécialiste en gestion des changements/adoption | | | |
> | Directeur de réseau | | | |
> | Directeur de la sécurité | | | |
> | Directeur de la téléphonie | | | |
> | Directeur de bureau | | | |
> | Responsable du support | | | |
> | Directeur du déploiement | | | |
> | Propriétaire de service | | | |
> | Responsable des sites | | | |
> | Responsable de l’équipe vidéo | | | |
> | Prospects d’unités commerciales | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 ou Office 365 détails de votre organisation

Il est vivement recommandé d’avoir une organisation Microsoft 365 ou Office 365 active lorsque vous travaillez à ce questionnaire. Si vous n’avez pas encore activé ou configuré Microsoft 365 ou Office 365 organisation, consultez la planifier votre configuration [d’Microsoft 365 entreprise.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

Utilisez le tableau suivant pour capturer des informations sur l Microsoft 365 ou Office 365 organisation.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Remarque de l’Microsoft 365<br/>ou Office 365 nom et ID de votre organisation<br/>dans la colonne Answer. Si vous avez d’autres<br/>plusieurs locataires associés<br/>votre organisation, notez tous les ID. | Nom du client : <br/>ID de locataire :| |
> | Dans quelles régions les locataires sont-ils déployés ?| | |
> | Notez le type de ces Microsoft 365 ou <br/>Office 365 de client. Sont-elles multitenantes ? <br/>ou dédié ? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> Dédié | |
> | Quels sont les produits Microsoft Online utilisés actuellement ? <br/>Notez le nombre d’utilisateurs activés pour chaque <br/>dans la colonne Commentaires. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype Entreprise <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint En ligne <br/> <input type="checkbox">OneDrive Entreprise <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> Autre| |
> | Quel niveau de licence est activé pour les Skype <br/>Utilisateurs Business Online ? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Nombre d’utilisateurs <br/>pour chaque référence SKU : |
> | Quelle est la forêt Active Directory actuelle ? <br/>niveau fonctionnel dans l’environnement ? <br/>S’il y a plusieurs forêts, notez les détails <br/>dans la colonne Commentaires. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Que utilisez-vous pour l’annuaire ? <br/>synchronisation aujourd’hui ? |<input type="checkbox"> Aucune synchronisation (cloud uniquement) <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Connecter <br/> <input type="checkbox"> Autre (spécifiez dans la <br/>&nbsp;&nbsp; &nbsp; Colonne Commentaires.)| |
> | L’identité fédérée est-elle déployée actuellement ? <br/>(Services de fédération Active Directory ou <br/>tiers) | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Si vous utilisez une identité fédérée, quelle est la <br/>d’infrastructure de fédération ? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows FS 2012 AD <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> Fédération tierce <br/>&nbsp;&nbsp; &nbsp; passerelle (notez les détails <br/>&nbsp;&nbsp; &nbsp; dans la colonne Commentaires.) | |
> | Si vous conservez actuellement une Microsoft 365<br/>ou Office 365 client, est le domaine SMTP/SIP de <br/>vos utilisateurs ciblés associés au client ? | <input type="checkbox">N/A – Pas de Microsoft 365 ou<br/>&nbsp;&nbsp; &nbsp; Office 365 client en place <br/> <input type="checkbox"> Non, smTP/SIP des utilisateurs <br/>&nbsp;&nbsp; &nbsp; domaine n’est pas associé <br/>&nbsp;&nbsp; &nbsp; avec n’importe quel client dans <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou Office 365<br/> <input type="checkbox"> Oui, le SMTP/SIP des utilisateurs <br/>&nbsp;&nbsp; &nbsp; domaine est associé <br/>&nbsp;&nbsp; &nbsp; avec un client existant dans <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou Office 365 | |
> | Les upN utilisateurs correspondent-ils à leur adresse SMTP principale ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non <br/> <input type="checkbox"> Incohérente | |

## <a name="existing-collaboration-platform-summary"></a>Résumé de la plateforme de collaboration existante

Utilisez le tableau suivant pour capturer des informations sur le déploiement de votre plateforme de collaboration existante.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Microsoft Teams est-il déployé ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Skype Entreprise est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous que <br/>vous notez la version et la mise à jour cumulative (CU) <br/>dans la colonne Commentaires. | <input type="checkbox">Oui, Microsoft 365 ou <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Oui, hybride (avec <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Oui, en local <br/> <input type="checkbox"> Oui, en ligne, dédié <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Oui, hébergé, dédié <br/>&nbsp;&nbsp; &nbsp; (tiers) <br/> <input type="checkbox"> Oui, hébergé, partagé <br/>&nbsp;&nbsp; &nbsp; (tiers) <br/> <input type="checkbox"> Non, autre | |
> | Exchange est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous que <br/>vous notez la version et les détails de la cu dans les Commentaires <br/>. | <input type="checkbox">Oui, Microsoft 365 <br/> <input type="checkbox"> Oui, hybride (avec <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Oui, en local <br/> <input type="checkbox"> Oui, en ligne, dédié <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Oui, hébergé, dédié <br/>&nbsp;&nbsp; &nbsp; (tiers) <br/> <input type="checkbox"> Oui, hébergé, partagé <br/>&nbsp;&nbsp; &nbsp; (tiers) <br/> <input type="checkbox"> Non, autre | |
> | SharePoint est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous que <br/>vous notez la version et les détails de la cu dans les Commentaires <br/>. | <input type="checkbox">Oui, Microsoft 365 <br/> <input type="checkbox"> Oui, hybride (avec <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 ou <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Oui, en local <br/> <input type="checkbox"> Oui, en ligne, dédié <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Oui, hébergé, dédié <br/>&nbsp;&nbsp; &nbsp; (tiers) <br/> <input type="checkbox"> Oui, hébergé, partagé <br/>&nbsp;&nbsp; &nbsp; (tiers) <br/> <input type="checkbox"> Non, autre | |
> | Votre OneDrive Entreprise est-elle déployée ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Avez-vous d’autres plateformes tierces déployées ? <br/>et en cours d’utilisation aujourd’hui ? Si c’est le cas, notez le nombre d’utilisateurs de <br/>ces plateformes et les informations d’utilisation dans la <br/>Colonne Commentaires. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Marge <br/> <input type="checkbox"> Autre (spécifiez dans la <br/>&nbsp;&nbsp; &nbsp; Colonne Commentaires.) | Nombre d’utilisateurs : <br/>Détails :|
> | Envisagez-vous de déplacer des utilisateurs de ces <br/>plateformes à Teams ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Quelle est la solution téléphonique et de conférence actuelle ? <br/>des utilisateurs qui sont dans l’étendue de cette initiative ? | | |
> | Avez-vous [des SBC qui supportent le routage direct](./direct-routing-plan.md#supported-session-border-controllers-sbcs) déployé ? <br/>pour les bureaux qui sont dans le cadre de cette initiative ? Si c’est le cas,<br/>notez les détails dans la colonne Commentaires.| <input type="checkbox"> Oui <br/> <input type="checkbox"> Non ||

## <a name="collaboration-platform-deployment-details"></a>Détails du déploiement de la plateforme de collaboration

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (le cas échéant)

Le cas échéant, capturez les détails de votre déploiement Teams à l’aide du tableau d’exemple ci-dessous. Si vous n’avez pas déployé d’Teams, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Pour quels types d’utilisateurs Teams est-il activé ? | <input type="checkbox"> Tous les utilisateurs de l’organisation <br/> <input type="checkbox"> Utilisateurs/groupes d’utilisateurs spécifiques <br/>&nbsp;&nbsp; &nbsp; (Spécifiez-le dans la colonne Commentaires.) ||
> | Quelles Teams et les différentes fonctionnalités sont en cours d’utilisation ? | <input type="checkbox"> Conversations basées sur les canaux <br/> <input type="checkbox"> Conversation privée <br/> <input type="checkbox"> Accès invité <br/> <input type="checkbox"> Réunions de canal <br/> <input type="checkbox"> Réunions privées <br/> <input type="checkbox"> Appels privés <br/> <input type="checkbox"> Rencontre de canal ad hoc <br/> <input type="checkbox"> Vidéos dans les réunions <br/> <input type="checkbox"> Partage d’écran dans les réunions <br/> <input type="checkbox"> Audioconférence <br/><input type="checkbox"> Applications (applications)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Onglets<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Connecteurs<br/><input type="checkbox"> Intégration du stockage cloud personnalisé <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Drive, Egnyte <br/> <input type="checkbox"> Intégration de la messagerie de canal <br/> <input type="checkbox"> Autre (spécifier dans la colonne Commentaires.) | |
> | Quelles applications avez-vous déployées sur Teams ? | | |
> | Avez-vous spécifiquement bloqué des fonctionnalités de Teams ? <br/>Si c’est le cas, notez les détails de la colonne Commentaires. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non ||
> | Quels sont les clients Teams utilisés ? | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows Mobile | |
> | Quelles sont les personnes autorisées à créer des équipes ? | <input type="checkbox"> Tous les membres de l’organisation <br/>&nbsp;&nbsp; &nbsp; (Il s’agit du paramètre par défaut) <br/> <input type="checkbox"> Personnes spécifiques <br/>&nbsp;&nbsp; &nbsp; (Spécifiez-le dans la colonne Commentaires.) | |
> | Utilisez-vous les fonctionnalités de sécurité et conformité dans Teams ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Entreprise Online (le cas échéant)

Le cas échéant, capturez les détails de votre déploiement Skype Entreprise Online à l’aide du tableau d’exemple ci-dessous. Si vous n’avez pas déployé de déploiement Skype Entreprise Online, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Types d’utilisateurs activés pour l’Skype <br/>entreprise Online ? | <input type="checkbox"> Tous les utilisateurs de l’organisation <br/> <input type="checkbox"> Utilisateurs/groupes d’utilisateurs spécifiques <br/>&nbsp;&nbsp; &nbsp; (Spécifiez-le dans la colonne Commentaires.) | |
> | Fonctionnalités et caractéristiques actuellement <br/>en cours d’utilisation aujourd’hui ? | <input type="checkbox"> Messagerie instantanée et présence (MI/P)<br/> <input type="checkbox"> Conférence <br/> <input type="checkbox"> Fédération <br/> <input type="checkbox"> Enregistrement de la réunion <br/> <input type="checkbox"> Audioconférence Microsoft <br/> <input type="checkbox"> Audioconférence tierce (Remarque<br/>&nbsp;&nbsp; &nbsp; détails dans la colonne Commentaires.) <br/> <input type="checkbox"> Forfaits d’appels (anciennement PSTN Calling) <br/> <input type="checkbox"> Attendant automatiques de l’organisation <br/> <input type="checkbox"> Files d’attente d’appels | |
> | Avez-vous spécifiquement bloqué des Skype pour <br/>Fonctionnalités de Business Online ? <br/>Si c’est le cas, notez les détails de la colonne Commentaires. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Quelle méthode utilisez-vous ou prévoyez-vous d’utiliser pour <br/>se Système téléphonique (anciennement CLOUD PBX) à <br/>le PSTN ? <br/>Sélectionnez toutes les sélections applicables. | <input type="checkbox"> Forfaits d’appels (anciennement PSTN Calling) <br/> <input type="checkbox"> Connectivité PSTN sur site <br/>&nbsp;&nbsp; &nbsp; (en tirant parti de la Skype de <br/>&nbsp;&nbsp; &nbsp; Business 2015 ou Lync Server <br/>&nbsp;&nbsp; &nbsp; Déploiement 2013) <br/> <input type="checkbox"> Connectivité PSTN sur site <br/>&nbsp;&nbsp; &nbsp; (à l’aide de Cloud Connector) | |
> | Avez-vous transféré des numéros de téléphone vers Microsoft ? <br/>Cela s’applique aux forfaits d’appels et au système audio <br/>Fonctionnalités de conférence. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype Entreprise local (le cas échéant)

Le cas échéant, capturez les détails de votre déploiement Skype Entreprise à l’aide du tableau d’exemple ci-dessous. Si vous n’avez pas déployé de Skype Entreprise local, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quelles versions de Lync ou d’Skype Entreprise <br/> sont actuellement déployés sur site ? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype Entreprise Server 2015 <br/> <input type="checkbox">Skype Entreprise Server 2019 <br/><input type="checkbox">Skype Entreprise Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Édition | |
> | La connectivité hybride avec Skype Entreprise Online est-elle configurée ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Cet environnement est-il hébergé et géré par un tiers ? <br/>vous fêtez ? Si c’est le cas, notez les détails dans la <br/>Colonne Commentaires. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Caractéristiques et fonctionnalités actuellement en cours d’utilisation <br/>aujourd’hui ? | <input type="checkbox"> Messagerie instantanée et présence (MI/P) <br/> <input type="checkbox"> Conférence <br/> <input type="checkbox"> Fédération <br/> <input type="checkbox"> Enregistrement de la réunion <br/> <input type="checkbox"> Conversation permanente/ conversation de groupe <br/> <input type="checkbox"> Audioconférence Microsoft <br/>&nbsp;&nbsp; &nbsp; (anciennement Conférence téléphonique) sur votre <br/>&nbsp;&nbsp; &nbsp; serveur Lync local ou <br/>&nbsp;&nbsp; &nbsp; Skype Entreprise déploiement <br/> <input type="checkbox"> Audioconférence tierce <br/>&nbsp;&nbsp; &nbsp; (Notez les détails dans les Commentaires <br/>&nbsp;&nbsp; &nbsp; .) <br/> <input type="checkbox">Voix Entreprise à l’aide de l’utilisation en local <br/>&nbsp; &nbsp; &nbsp;Connectivité PSTN <br/> <input type="checkbox"> Forfaits d’appels (anciennement PSTN Calling) via <br/>&nbsp;&nbsp; &nbsp; Hybride avec Skype Entreprise Online | |
> | Quelle(s) version(s) du serveur Edge avez-vous déployé ? | <input type="checkbox">Office Communications Server 2007 « R1 » <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype Entreprise Server 2015 <br/> <input type="checkbox">Skype Entreprise Server 2019| |
> | Avez-vous Lync ou Skype Entreprise Edge ? <br/>déployé dans plusieurs centres de données ? <br/>Si c’est le cas, notez les détails de la colonne Commentaires. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Sélectionnez les services que fournit aujourd’hui votre rôle Edge. | <input type="checkbox"> Accès des utilisateurs externes (utilisateurs d’entreprise) <br/> <input type="checkbox"> Accès des utilisateurs distants (anonyme) <br/>&nbsp;&nbsp; &nbsp; participants à la réunion externe) <br/> <input type="checkbox"> Fédération <br/> <input type="checkbox"> Relais multimédia | |
> | Quelles sont les fonctionnalités d’appel vocal suivantes ? <br/>vous avez actuellement des dépendances ? <br/>Notez les dépendances supplémentaires dans les Commentaires <br/>. | <input type="checkbox"> Options occupé(s) <br/> <input type="checkbox"> Call park <br/> <input type="checkbox"> Récupérer un appel ou un appel de groupe <br/> <input type="checkbox"> Téléphones de zone communs ou « hot desking » <br/> <input type="checkbox"> Response Groups ou groupes de recherche <br/> <input type="checkbox"> Apparence de ligne partagée <br/> <input type="checkbox"> Ligne privée <br/> <input type="checkbox"> Messagerie vocale <br/> <input type="checkbox"> Appeler au travail <br/> <input type="checkbox"> Numéros d’urgence ou d’informations <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Numérotation par extension <br/> <input type="checkbox"> Standard automatique <br/> <input type="checkbox"> Accès des abonnés <br/> <input type="checkbox"> Périphériques analogiques <br/> <input type="checkbox"> Télécopie <br/> <input type="checkbox"> ID de l’appelant masquage ou modification <br/> <input type="checkbox"> Routage basé sur l’emplacement <br/> <input type="checkbox"> Routage le moins coûteux <br/> <input type="checkbox"> Téléphones cellulaires | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Réseaux et accès aux services Microsoft 365 et Office 365 réseau

Utilisez le tableau suivant pour capturer les détails réseau de votre organisation et la manière dont vos utilisateurs sont (ou seront) connectés aux services Microsoft 365 et Office 365 réseau.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Comment (ou comment) les utilisateurs dans l’étendue de la migration <br/>accéder Teams au bureau ? <br/>Sélectionnez toutes les sélections applicables. | <input type="checkbox"> Connexion NAT acheminée <br/> <input type="checkbox"> Serveur proxy <br/> <input type="checkbox"> Public Wi-Fi <br/> <input type="checkbox"> Gestion (non publique) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Peering Microsoft) ||
> | Si l’accès à Microsoft 365 ou Office 365 est accessible via une<br/>serveur proxy, existe-t-il un moyen d’ignorer le proxy ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | ExpressRoute est-il utilisé actuellement ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non <br/> <input type="checkbox"> Non, mais il est planifié | |
> | Avez-vous effectué une évaluation de la disponibilité du réseau ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Les utilisateurs doivent-ils utiliser un réseau privé virtuel (VPN) lors de la connexion à <br/>ressources de l’entreprise à distance ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | En cas d’utilisation d’un réseau privé virtuel (VPN), Teams en exclure le trafic <br/>le VPN pour accéder directement aux Microsoft 365 et Office 365 réseau privé ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Votre réseau prend-il en charge QoS ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Pouvez-vous hiérarchiser Teams trafic audio et vidéo ? <br/>pour une expérience de haute qualité ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Faire en sorte que tous les emplacements au sein d’une région ont une sortie Internet, <br/>ou la sortie Internet est-elle centralisée pour la région entière ? | <input type="checkbox"> Accès régional à Internet <br/> <input type="checkbox"> Accès centralisé au <br/>&nbsp;&nbsp; &nbsp; internet | |

## <a name="endpoints"></a>Points de terminaison

Utilisez le tableau suivant pour capturer les détails des clients et points de terminaison utilisés.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quel système d’exploitation de bureau les utilisateurs utilisent-ils ? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Spécifiez la version dans la colonne Commentaires).) <br/> <input type="checkbox"> Linux (spécifiez la distribution dans la colonne Commentaires). <br/><input type="checkbox"> Autre (Notez les détails dans la colonne Commentaires.) | |
> | Quelle version d’Microsoft Office est déployée <br/>à ces appareils ? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office pour Mac 2011 <br/> <input type="checkbox">Office pour Mac 2016 <br/> <input type="checkbox"> Autre (Notez les détails dans la colonne Commentaires.) | |
> | Quelle Office technologie de déploiement utilisée <br/>dans votre organisation ? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Click-to-Run | |
> | Quelles sont les applications mobiles autorisées et prise en charge ? <br/>plateformes en cours d’utilisation ? <br/>Sélectionnez toutes les sélections applicables. | <input type="checkbox">Windows <br/> <input type="checkbox"> Mobile <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Autre (Notez les détails dans la colonne Commentaires.) | |
> | Comment les appareils mobiles sont-ils fournis ? <br/>Sélectionnez toutes les sélections applicables. | <input type="checkbox"> Appareils d’entreprise <br/> <input type="checkbox"> Apportez votre propre appareil | |
> | Quels appareils les utilisateurs utilisent-ils actuellement pour accéder à <br/>services de voix et de conférence <br/>(combinés, casques, téléphones, vidéo) ? | | |

## <a name="operations"></a>Opérations

Utilisez le tableau suivant pour capturer les détails des aspects opérationnels de votre environnement.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quel est votre modèle d’opérations pour votre serveur Lync ? <br/>Skype Entreprise Server, Microsoft 365 déploiement, <br/>ou Office 365 dès aujourd’hui ? | | |
> | Pouvez-vous définir la disposition de support actuelle pour <br/>Lync Server, Skype Entreprise Server, Microsoft 365, <br/>ou Office 365 ? | | |
> | Si vous déployez vers plusieurs pays ou régions, <br/>chaque pays/région possède-t-il son propre service it/téléphonique ? <br/>du personnel enseignant, ou ces services seront-ils gérés de manière centralisée ? | <input type="checkbox"> Opérations régionales et support <br/> <input type="checkbox"> Opérations et support centralisés | |
> | Suivez-vous la méthodologie de qualité des appels ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Avez-vous affecté une personne ou une équipe au <br/>Rôle Quality Champion pour la plateforme de collaboration <br/>en cours d’utilisation ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non ||
> | Comment surveiller votre serveur Lync, à Skype <br/>Business Server, Microsoft 365 déploiement, ou <br/>Office 365 déploiement ? | | |
> | Avez-vous des problèmes de qualité des appels ? | <input type="checkbox"> Oui<br/> <input type="checkbox"> Non | |
> | Comment et quand fournissez-vous une formation à votre <br/>du service d’aide sur les nouveaux services et fonctionnalités ? | | |

## <a name="adoption-and-readiness"></a>Adoption et préparation

Utilisez le tableau suivant et consignez l’état d’adoption et de préparation actuel de votre organisation.

>
> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quelle est votre utilisation active actuelle de <br/>Skype Entreprise? | **__ %** du nombre total d’utilisateurs actifs par rapport aux utilisateurs activés | |
> | Comment votre organisation utilise-t-elle ? <br/>Skype Entreprise? | Conversations en tête-à-tête <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Messagerie instantanée <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Appels <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Partage<br/> Réunions <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conférence<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Partage<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Appels | |
> | Votre organisation a-t-elle une adoption par les utilisateurs ? <br/>et de l’équipe de gestion des changements ? | <input type="checkbox"> Oui<br/> <input type="checkbox"> Non | |
> | Comment mesurer actuellement le succès de la technologie <br/>déploiements tels que Skype Entreprise ? | | |
> | Quel est le pourcentage de votre base d’utilisateurs ? <br/>adoptées Skype Entreprise ? | | |
> | Quelle est l’opinion des utilisateurs concernant Skype Entreprise ? | <input type="checkbox"> Bonne <br/> <input type="checkbox"> Neutre <br/> <input type="checkbox"> Mauvaises | |
> | Laquelle des descriptions suivantes décrit le mieux le déploiement <br/>utilisée pour votre stratégie de Skype Entreprise <br/>déploiement ? | <input type="checkbox"> Grande portée : campagne par courrier électronique avec <br/>&nbsp;&nbsp; &nbsp; Liens vers la formation <br/> <input type="checkbox"> Développé : large portée plus une grande variété <br/>&nbsp;&nbsp; &nbsp; de campagnes de sensibilisation (posters, <br/>&nbsp;&nbsp; &nbsp; épreuves, champions) et formation <br/>&nbsp;&nbsp; &nbsp; (vidéos, guides de l’utilisateur, en personne) <br/> <input type="checkbox"> Adapté : étendu, plus ciblé <br/>&nbsp;&nbsp; &nbsp; Messagerie et formation par personnage <br/> <input type="checkbox"> Autre <br/>&nbsp;&nbsp; &nbsp; (Notez les détails dans la colonne Commentaires.) | |
