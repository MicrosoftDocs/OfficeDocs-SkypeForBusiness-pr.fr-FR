---
title: '| de mise à niveau de Microsoft Teams Évaluation de l’environnement, questions sur la découverte'
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Utilisez ces conseils pour en savoir plus sur les conditions requises pour évaluer correctement votre environnement actuel pour la mise à niveau vers Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a72fda2622ab9bcd56520e48db38335d72423e46
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616030"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>Questionnaire de découverte - Évaluer votre environnement

L’ensemble de tables suivant répertorie les questions qui vous aideront à [évaluer votre environnement avant la mise à niveau vers Teams](upgrade-plan-journey-evaluate-environment.md) :

- [Détails de l’organisation Microsoft 365 ou Office 365](#microsoft-365-or-office-365-organization-details)
- [Résumé de la plateforme de collaboration existante](#existing-collaboration-platform-summary)
- [Détails du déploiement de la plateforme de collaboration](#collaboration-platform-deployment-details)
- [Mise en réseau et accès aux services Microsoft 365 ou Office 365](#networking-and-access-to-microsoft-365-or-office-365-services)
- [Points de terminaison](#endpoints)
- [Opérations](#operations)
- [Adoption et préparation](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Détails de l’organisation Microsoft 365 ou Office 365

Nous vous recommandons vivement d’avoir une organisation Microsoft 365 ou Office 365 active lorsque vous travaillez avec le questionnaire. Si vous n’avez pas encore activé ou configuré une organisation Microsoft 365 ou Office 365, consultez [Planifier votre configuration de Microsoft 365 pour les entreprises](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Utilisez le tableau suivant pour capturer des informations sur l’organisation Microsoft 365 ou Office 365.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Notez l’organisation de production Microsoft 365 ou Office 365 <br>nom et ID dans la colonne Réponse <br/>Si vous avez plusieurs locataires <br>associé à votre organisation, <br>Notez tous les ID. | Nom du locataire : <br/>ID de locataire :| |
> | Dans quelles régions les locataires sont-ils déployés ?| | |
> | Ces locataires Sont-ils Microsoft 365 ou Office 365 multilocataire ou <br>Dédié? | <input type="checkbox"> Multilocataire<br/> <input type="checkbox"> Dédié | |
> | Quels sont les produits Microsoft Online utilisés actuellement ? <br/>Notez le nombre d’utilisateurs activés pour chaque <br>dans la colonne Commentaires. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">Skype Entreprise <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">OneDrive Entreprise <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Autres| |
> | Quel niveau de licence est activé pour Skype ? <br>Utilisateurs d’Entreprise Online ? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> Autonome | Nombre d’utilisateurs <br>pour chaque référence SKU : |
> | Qu’est-ce que la forêt Active Directory actuelle ? <br>niveau fonctionnel dans l’environnement ? <br/>S’il y a plusieurs forêts, notez les détails <br>dans la colonne Commentaires. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Que utilisez-vous pour le répertoire ? <br>synchronisation aujourd’hui ? |<input type="checkbox"> Aucune synchronisation (cloud uniquement) <br/> <input type="checkbox"> Azure Active Directory <br>&nbsp;&nbsp; &nbsp; Connecter <br/> <input type="checkbox"> Autre (spécifier dans le <br>&nbsp;&nbsp; &nbsp; Colonne Commentaires.)| |
> | L’identité fédérée est-elle déployée actuellement ? <br/>(Services ADFS ou <br>tiers) | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Si vous utilisez une identité fédérée, quel est le <br>l’infrastructure de fédération ? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Fédération tierce <br>&nbsp;&nbsp; &nbsp;Passerelle <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans le <br>&nbsp;&nbsp; &nbsp; Colonne Commentaires.) | |
> | Si vous gérez actuellement une version active de Microsoft 365 ou Office 365 <br>client, est le domaine SMTP/SIP de votre <br>utilisateurs ciblés associés au locataire ? | <input type="checkbox">N/A : Aucun Microsoft 365 ou Office 365 <br>&nbsp;&nbsp; &nbsp;locataire en place <br/> <input type="checkbox"> Non, SMTP/SIP des utilisateurs <br>&nbsp;&nbsp; &nbsp;le domaine n’est pas associé <br>&nbsp;&nbsp; &nbsp;avec tous les locataires dans <br>&nbsp;&nbsp; &nbsp; Microsoft 365 ou Office 365 <br/> <input type="checkbox"> Oui, SMTP/SIP des utilisateurs <br>&nbsp;&nbsp; &nbsp;domaine associé <br>&nbsp;&nbsp; &nbsp;avec un locataire existant <br>&nbsp;&nbsp; &nbsp;dans Microsoft 365 ou Office 365 | |
> | Les upN utilisateur correspondent-ils à leur adresse SMTP principale ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non <br/> <input type="checkbox"> Incohérent | |

## <a name="existing-collaboration-platform-summary"></a>Résumé de la plateforme de collaboration existante

Utilisez le tableau suivant pour capturer des informations sur le déploiement de votre plateforme de collaboration existante.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Microsoft Teams est-il déployé ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Skype Entreprise est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous <br>vous notez la version et la mise à jour cumulative (CU) <br>détails dans la colonne Commentaires. | <input type="checkbox">Oui, Microsoft 365 ou Office 365 <br/> <input type="checkbox">Oui, hybride (avec Microsoft 365 ou Office 365) <br/> <input type="checkbox"> Oui, localement <br/> <input type="checkbox"> Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Oui, hébergé, dédié <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox"> Oui, hébergé, partagé (tiers) <br/> <input type="checkbox"> Non, autre | |
> | Exchange est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous <br>vous notez la version et les détails cu dans les commentaires <br>Colonne. | <input type="checkbox">Oui, Microsoft 365 ou Office 365 <br/> <input type="checkbox">Oui, hybride (avec Microsoft 365 ou Office 365) <br/> <input type="checkbox"> Oui, localement <br/> <input type="checkbox"> Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Oui, hébergé, dédié <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox"> Oui, hébergé, partagé <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox"> Non, autre | |
> | SharePoint est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous <br>vous notez la version et les détails cu dans les commentaires <br>Colonne. | <input type="checkbox">Oui, Microsoft 365 ou Office 365 <br/> <input type="checkbox">Oui, hybride (avec Microsoft 365 ou Office 365) <br/> <input type="checkbox"> Oui, localement <br/> <input type="checkbox"> Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Oui, hébergé, dédié <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox"> Oui, hébergé, partagé <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox"> Non, autre | |
> | Microsoft 365 ou Office 365 OneDrive Entreprise est-il déployé ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Avez-vous d’autres plateformes tierces déployées ? <br>et en service aujourd’hui ? Si c’est le cas, notez le nombre d’utilisateurs de <br>ces plateformes et les détails d’utilisation dans les commentaires <br>Colonne. | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> Mou <br/> <input type="checkbox"> Autre (spécifier dans les commentaires <br>&nbsp;&nbsp; &nbsp;colonne.) | Nombre d’utilisateurs : <br/>Détails:|
> | Envisagez-vous de déplacer des utilisateurs de ces <br>plateformes vers Teams ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Quelle est la solution de téléphonie et de conférence actuelle ? <br>des utilisateurs concernés par cette initiative ? | | |
> | Avez-vous [des SBC qui prennent en charge le routage direct](direct-routing-plan.md#supported-session-border-controllers-sbcs) déployé pour vos bureaux qui sont dans l’étendue de cette initiative ? <br>Si c’est le cas, notez les détails de la colonne Commentaires.| <input type="checkbox"> Oui <br/> <input type="checkbox"> Non ||

## <a name="collaboration-platform-deployment-details"></a>Détails du déploiement de la plateforme de collaboration

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (le cas échéant)

Le cas échéant, capturez les détails de votre déploiement Teams à l’aide de l’exemple de tableau ci-dessous. Si vous n’avez pas déployé Teams, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Pour quels types d’utilisateurs Teams est-il activé ? | <input type="checkbox"> Tous les utilisateurs de l’organisation <br/> <input type="checkbox"> Utilisateurs/groupes d’utilisateurs spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne Commentaires) ||
> | Quelles fonctionnalités et modalités Teams sont utilisées ? | <input type="checkbox"> Conversations basées sur un canal <br/> <input type="checkbox"> Conversation privée <br/> <input type="checkbox"> Accès invité <br/> <input type="checkbox"> Réunions de canal <br/> <input type="checkbox"> Réunions privées <br/> <input type="checkbox"> Appel privé <br/> <input type="checkbox"> Meetup de canal ad hoc <br/> <input type="checkbox"> Vidéos dans les réunions <br/> <input type="checkbox"> Partage d’écran dans les réunions <br/> <input type="checkbox"> Audioconférence <br/><input type="checkbox"> Applications (applications)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Onglets<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Connecteurs<br><input type="checkbox"> Intégration du stockage cloud personnalisé <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google Drive, Egnyte <br/> <input type="checkbox"> Intégration de la messagerie de canal <br/> <input type="checkbox"> Autre (spécifier dans la colonne Commentaires.) | |
> | Quelles applications avez-vous déployées dans Teams ? | | |
> | Avez-vous spécifiquement bloqué des fonctionnalités de Teams ? <br/>Si c’est le cas, notez les détails de la colonne Commentaires. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non ||
> | Quels sont les clients Teams utilisés ? | <input type="checkbox"> Web <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Quelles sont les personnes autorisées à créer des équipes ? | <input type="checkbox"> Tous les membres de l’organisation <br>&nbsp;&nbsp; &nbsp;(Il s’agit du paramètre par défaut) <br/> <input type="checkbox"> Personnes spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne Commentaires.) | |
> | Utilisez-vous les fonctionnalités de sécurité et conformité dans Teams ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Entreprise Online (le cas échéant)

Le cas échéant, capturez les détails de votre déploiement Skype Entreprise Online à l’aide de l’exemple de tableau ci-dessous. Si vous n’avez pas déployé Skype Entreprise déploiement en ligne, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quels types d’utilisateurs sont activés pour Skype <br>for Business Online ? | <input type="checkbox"> Tous les utilisateurs de l’organisation <br/> <input type="checkbox"> Utilisateurs/groupes d’utilisateurs spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne Commentaires) | |
> | Quelles sont actuellement les modalités et les fonctionnalités <br>en service aujourd’hui ? | <input type="checkbox"> Messagerie instantanée et présence (IM/P)<br/> <input type="checkbox"> Réunions <br/> <input type="checkbox"> Fédération <br/> <input type="checkbox"> Enregistrement de réunion <br/> <input type="checkbox"> Audioconférence Microsoft <br/> <input type="checkbox"> Audioconférence tierce <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans la colonne Commentaires.) <br/> <input type="checkbox"> Forfaits d’appels (anciennement appel RTC) <br/> <input type="checkbox"> Standards automatiques de l’organisation <br/> <input type="checkbox"> Files d’attente d’appels | |
> | Avez-vous bloqué spécifiquement skype pour <br>Fonctionnalités Business Online ? <br>Si c’est le cas, notez les détails de la colonne Commentaires. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Quelle méthode utilisez-vous ou envisagez-vous d’utiliser ? <br>connect Phone System (anciennement Cloud PBX) à <br>le RTC ? <br/>Sélectionnez tout ce qui s’applique. | <input type="checkbox"> Forfaits d’appels (anciennement appel RTC) <br/> <input type="checkbox"> Connectivité PSTN locale (tirant parti de la connectivité existante) <br>&nbsp;&nbsp; &nbsp;Skype Entreprise 2015 ou Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;déploiement) <br/> <input type="checkbox"> Connectivité PSTN locale (à l’aide du connecteur cloud) | |
> | Avez-vous transféré des numéros de téléphone vers Microsoft ? <br/>Cela s’applique aux forfaits d’appels et à l’audio <br>Fonctionnalités de conférence. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype Entreprise localement (le cas échéant)

Le cas échéant, capturez les détails de votre déploiement Skype Entreprise à l’aide de l’exemple de tableau ci-dessous. Si vous n’avez pas déployé Skype Entreprise localement, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quelles versions de Lync ou Skype Entreprise actuellement ? <br>sont-ils déployés localement ? | <input type="checkbox"> Office Communications Server 2007 « R1 » <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype Entreprise Server 2015 <br/> <input type="checkbox">Skype Entreprise Server 2019 <br/> <input type="checkbox">Skype Entreprise Cloud Connector Edition | |
> | La connectivité hybride avec Skype Entreprise Online est-elle configurée ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Cet environnement est-il hébergé et géré par un tiers ? <br/>Si c’est le cas, notez les détails de la colonne Commentaires. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Modalités et fonctionnalités actuellement utilisées <br>Aujourd'hui? | <input type="checkbox"> Messagerie instantanée et présence (IM/P) <br/> <input type="checkbox"> Réunions <br/> <input type="checkbox"> Fédération <br/> <input type="checkbox"> Enregistrement de réunion <br/> <input type="checkbox"> Conversation permanente / Conversation de groupe <br/> <input type="checkbox"> Audioconférence Microsoft <br>&nbsp;&nbsp; &nbsp;(anciennement Dial in Conferencing) sur votre <br>&nbsp;&nbsp; &nbsp;serveur Lync local ou <br>&nbsp;&nbsp; &nbsp;déploiement Skype Entreprise <br/> <input type="checkbox"> Audioconférence tierce <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans la colonne Commentaires) <br/> <input type="checkbox">Voix Entreprise l’utilisation d’un rtc local <br>&nbsp;&nbsp; &nbsp;Connectivité <br/> <input type="checkbox"> Forfaits d’appels (anciennement appel RTC) via <br>&nbsp;&nbsp; &nbsp; Hybride avec Skype Entreprise Online | |
> | Quelle(s) version(s) du serveur Edge avez-vous déployé ? | <input type="checkbox"> Office Communications Server 2007 « R1 » <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype Entreprise Server 2015 <br/> <input type="checkbox">Skype Entreprise Server 2019 | |
> | Avez-vous déployé Lync ou Skype Entreprise Edge ? <br>dans plusieurs centres de données ? <br/>Si c’est le cas, notez les détails de la colonne Commentaires. | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Sélectionnez les services que votre rôle Edge fournit aujourd’hui. | <input type="checkbox"> Accès des utilisateurs externes (utilisateurs d’entreprise) <br/> <input type="checkbox"> Accès utilisateur distant (externe anonyme) <br>&nbsp;&nbsp; &nbsp;participants à la réunion) <br/> <input type="checkbox"> Fédération <br/> <input type="checkbox"> Relais multimédia | |
> | Parmi les fonctionnalités d’appel vocal suivantes, laquelle avez-vous <br>actuellement des dépendances ? <br/>Notez les dépendances supplémentaires dans les commentaires <br>Colonne. | <input type="checkbox"> Options de disponibilité <br/> <input type="checkbox"> Parc d’appels <br/> <input type="checkbox"> Prise d’appel ou prise d’appel de groupe <br/> <input type="checkbox"> Téléphones de zone commune, ou « desking chaud » <br/> <input type="checkbox"> Groupes de réponses ou groupes de chasse <br/> <input type="checkbox"> Apparence de ligne partagée <br/> <input type="checkbox"> Ligne privée <br/> <input type="checkbox"> Messagerie vocale <br/> <input type="checkbox"> Appeler via le travail <br/> <input type="checkbox"> Numéros d’urgence ou d’informations <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox"> Numérotation d’extension <br/> <input type="checkbox"> Standard automatique <br/> <input type="checkbox"> Accès de l’abonné <br/> <input type="checkbox"> Périphériques analogiques <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Masquage ou modification de l’ID de l’appelant <br/> <input type="checkbox"> Routage basé sur l’emplacement <br/> <input type="checkbox"> Routage à moindre coût <br/> <input type="checkbox"> Téléphones d’ascenseur | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Mise en réseau et accès aux services Microsoft 365 ou Office 365

Utilisez le tableau suivant pour capturer les détails de mise en réseau de votre organisation et la façon dont vos utilisateurs sont (ou seront) connectés aux services Microsoft 365 ou Office 365.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Comment faire (ou comment) les utilisateurs dans l’étendue de la migration <br>accéder à Teams lorsqu’ils sont au bureau ? <br/>Sélectionnez tout ce qui s’applique. | <input type="checkbox"> Connexion NAT routée <br/> <input type="checkbox"> Serveur proxy <br/> <input type="checkbox"> Wi-Fi publique <br/> <input type="checkbox"> Wi-Fi managées (non publiques) <br/> <input type="checkbox"> ExpressRoute (Peering Microsoft) ||
> | Si l’accès à Microsoft 365 ou Office 365 se fait via un serveur proxy, existe-t-il <br>un moyen de contourner le proxy ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | ExpressRoute est-il utilisé actuellement ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non <br/> <input type="checkbox"> Non, mais c’est planifié. | |
> | Avez-vous effectué une évaluation de la préparation du réseau ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Les utilisateurs doivent-ils utiliser un VPN lors de la connexion à <br>ressources d’entreprise à distance ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Si un VPN est utilisé, le trafic Teams peut-il être exclu de <br>le VPN pour accéder directement à Microsoft 365 ou Office 365 Services ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Votre réseau prend-il en charge QoS ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Pouvez-vous hiérarchiser le trafic audio et vidéo Teams <br>pour une expérience de haute qualité ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Tous les emplacements d’une région ont-ils une sortie Internet, <br>ou la sortie Internet est-elle centralisée pour l’ensemble de la région ? | <input type="checkbox"> Accès régional à Internet <br/> <input type="checkbox"> Accès centralisé à Internet | |

## <a name="endpoints"></a>Points de terminaison

Utilisez le tableau suivant pour capturer les détails des clients et des points de terminaison utilisés.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quel système d’exploitation de bureau les utilisateurs utilisent-ils ? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (spécifiez la version dans la colonne Commentaires.) <br/> <input type="checkbox"> Linux (spécifiez la distribution dans la colonne Commentaires.) <br/> <input type="checkbox"> Autre (Notez les détails dans la colonne Commentaires.) | |
> | Quelle version de Microsoft Office est déployée <br>sur ces appareils ? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Office pour Mac 2011 <br/> <input type="checkbox">Office pour Mac 2016 <br/> <input type="checkbox"> Autre (Notez les détails dans la colonne Commentaires.) | |
> | Quelle technologie de déploiement Office est utilisée ? <br>dans votre organisation ? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Démarrer en un clic | |
> | Quels sont les appareils mobiles autorisés et pris en charge ? <br>plateformes utilisées ? <br/>Sélectionnez tout ce qui s’applique. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Mobile <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Autre (Notez les détails dans la colonne Commentaires.) | |
> | Comment les appareils mobiles sont-ils fournis ? <br/>Sélectionnez tout ce qui s’applique. | <input type="checkbox"> Appareils d’entreprise <br/> <input type="checkbox"> Apportez votre propre appareil | |
> | Quels appareils les utilisateurs utilisent-ils actuellement pour accéder ? <br>services de voix et de conférence <br>(combinés, casques, téléphones, vidéo) ? | | |

## <a name="operations"></a>Opérations

Utilisez le tableau suivant pour capturer les détails des aspects opérationnels de votre environnement.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quel est votre modèle d’opérations pour votre serveur Lync, <br>déploiement Skype Entreprise Server, Microsoft 365 ou Office 365 <br>Aujourd'hui? | | |
> | Pouvez-vous décrire l’arrangement de support actuel pour <br>Lync Server, Skype Entreprise Server, Microsoft 365 ou Office 365 ? | | |
> | Si vous effectuez un déploiement dans plusieurs pays ou régions, <br>chaque pays/région a-t-il sa propre informatique/téléphonie ? <br>avec qui travailler, ou est-ce que cela sera géré de manière centralisée? | <input type="checkbox"> Opérations et support régionaux <br/> <input type="checkbox"> Opérations et prise en charge centralisées | |
> | Suivez-vous la [méthodologie de qualité des appels](quality-of-experience-review-guide.md) ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non | |
> | Avez-vous affecté une personne ou une équipe au <br>Rôle champion de la qualité pour la plateforme de collaboration <br>en service ? | <input type="checkbox"> Oui <br/> <input type="checkbox"> Non ||
> | Comment surveiller votre serveur Lync Server, Skype pour <br>Business Server, Microsoft 365 ou Office 365 déploiement ? | | |
> | Avez-vous des problèmes de qualité des appels ? | <input type="checkbox"> Oui<br/> <input type="checkbox"> Non | |
> | Comment et quand fournissez-vous une formation à votre <br>support technique sur les nouveaux services et fonctionnalités ? | | |

## <a name="adoption-and-readiness"></a>Adoption et préparation

Utilisez le tableau suivant et consignez l’état d’adoption et de préparation actuel de votre organisation.

>
> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quelle est votre utilisation active actuelle de <br>Skype Entreprise ? | **__** % du nombre total d’utilisateurs actifs par rapport aux utilisateurs activés | |
> | Comment votre organisation utilise-t-elle <br>Skype Entreprise ? | Conversations en tête-à-tête <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Appel <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Partage<br> Réunions <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conférence<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Partage<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Appel | |
> | Votre organisation a-t-elle une adoption par l’utilisateur ? <br>et l’équipe de gestion des modifications ? | <input type="checkbox"> Oui<br/> <input type="checkbox"> Non | |
> | Comment mesurez-vous actuellement la réussite de la technologie ? <br>déploiements comme Skype Entreprise ? | | |
> | Quel pourcentage de votre base d’utilisateurs diriez-vous a <br>adopté Skype Entreprise? | | |
> | Quelle est l’opinion des utilisateurs concernant Skype Entreprise ? | <input type="checkbox"> Bon <br/> <input type="checkbox"> Neutre <br/> <input type="checkbox"> Mauvais | |
> | Parmi les éléments suivants, lequel décrit le mieux le déploiement <br>stratégie utilisée pour votre Skype Entreprise <br>Déploiement? | <input type="checkbox"> Large portée : Campagne par e-mail avec <br>&nbsp;&nbsp; &nbsp;liens vers la formation <br/> <input type="checkbox"> Développé : large portée plus une variété <br>&nbsp;&nbsp; &nbsp;campagnes de sensibilisation (affiches, <br>&nbsp;&nbsp; &nbsp;événements, champions) et formation <br>&nbsp;&nbsp; &nbsp;(vidéos, guides utilisateur, en personne) <br/> <input type="checkbox"> Adapté : développé, plus ciblé <br>&nbsp;&nbsp; &nbsp;messagerie et formation par personnage <br/> <input type="checkbox"> Autres <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans la colonne Commentaires.) | |


