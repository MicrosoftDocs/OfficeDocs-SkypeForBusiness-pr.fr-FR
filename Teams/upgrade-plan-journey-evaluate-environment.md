---
title: Mise à niveau de Microsoft teams | Évaluation de l’environnement, questions de découverte
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Suivez ces instructions pour en savoir plus sur la configuration requise pour évaluer votre environnement actuel et procéder à la mise à niveau vers Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d73c40ee6a2ebe906a6a3ca66dbb430b843c6eeb
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706924"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>Évaluez votre environnement avant de procéder à la mise à niveau vers teams

![Diagramme de route de mise à niveau, mettant l’accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de la mise à niveau, en mettant l’accent sur l’étape de préparation technique")

Cet article fait partie de l’étape de préparation technique de votre mouvement de mise à niveau, une activité que vous finalisez en parallèle avec l’étape de préparation de l’utilisateur. Avant de continuer, assurez-vous d’avoir suivi les étapes ci-dessous :

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Cet article fournit une vue d’ensemble de la configuration requise pour évaluer correctement votre environnement actuel pour les équipes d’exploitation. L’évaluation de votre environnement vous permet d’identifier les risques et les exigences qui influenceront votre déploiement global. En identifiant ces éléments à l’aide de la commande, vous pouvez ajuster la planification du succès.

## <a name="introduction-to-the-discovery-questionnaire"></a>Présentation du questionnaire de découverte

Pour obtenir les résultats de votre clé objective (OKRs), vous avez déjà effectué des décisions relatives aux services clés. L’étape suivante consiste à effectuer une recherche environnementale pour évaluer tous les aspects relatifs à votre infrastructure, au réseau et aux opérations informatiques pour vérifier que votre organisation est prête à implémenter la solution. La découverte est l’une des principales étapes principales que vous prenez lors de la planification de votre voyage vers Teams. La découverte environnementale doit inclure une évaluation de la compatibilité réseau pour s’assurer que votre réseau peut prendre en charge la mise à niveau vers Teams. Vous effectuez une découverte détaillée de votre environnement pour mieux comprendre son état actuel et révéler les difficultés ou, d’autant plus importants, les bloqueurs possibles d’exécution de votre déploiement d’équipes.

Vous identifiez les risques techniques dans le cadre d’une analyse environnementale et de l’évaluation de l’adoption, et vous développez un plan d’atténuation pour chaque risque identifié. Vous devez incorporer ces informations dans le registre de risques.

Toutes les questions liées à votre infrastructure de collaboration existante 365 et au client, au réseau, aux points de terminaison, aux points de terminaison, aux opérations et à l’adoption et à la disponibilité font partie du questionnaire de découverte environnementale. Ce questionnaire est divisé en plusieurs sections pour vérifier la préparation de votre organisation à votre déploiement d’équipes dans plusieurs domaines importants. Collaborer avec votre équipe de projet pour fournir les informations demandées autant de détails que possible pour faciliter vos activités de planification.

> [!TIP]
> Vous pouvez commencer par copier le questionnaire dans un document Microsoft Word. Essayez de répondre à toutes vos questions et de capturer tous les détails lors de votre déplacement.

## <a name="project-team"></a>Équipe de projet

Assurez-vous d’avoir engagé les personnes appropriées à votre équipe de projet. Vérifiez les étapes achevées dans [inscrire votre projet stakekholders](upgrade-enlist-stakeholders.md).

## <a name="office-365-tenant-details"></a>Détails du client Office 365

Nous vous recommandons vivement d’avoir un client Office 365 actif lorsque vous travaillez avec ce questionnaire. Si vous n’avez pas encore activé ou configuré un client Office 365, voir [planifier votre installation d’office 365 pour les entreprises](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Utilisez le tableau suivant pour capturer des informations sur le client Office 365.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Notez le client Office 365 de production <br>nom et ID dans la colonne réponse <br/>Si vous avez plusieurs clients <br>associée à votre organisation, <br>Notez tous les ID. | Nom du client : <br/>ID de locataire :| |
> | Dans quelles régions les clients sont-ils déployés ?| | |
> | Ces clients sont-ils Office 365 ou <br>Spéciale? | <input type="checkbox">Mutualisée<br/> <input type="checkbox">Spéciale | |
> | Quels sont les produits Microsoft Online utilisés actuellement ? <br/>Notez le nombre d’utilisateurs activés pour chacun d’eux. <br>service dans la colonne commentaires. | <input type="checkbox">Microsoft teams <br/> <input type="checkbox">Skype entreprise <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive entreprise <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Ailleurs| |
> | Le niveau de licence est activé pour Skype pour <br>Utilisateurs de Business Online ? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">Version | Le nombre d’utilisateurs <br>pour chaque référence (SKU) : |
> | Qu’est-ce que la forêt Active Directory actuelle ; <br>niveau fonctionnel dans l’environnement ? <br/>S’il existe plusieurs forêts, notez les détails. <br>dans la colonne commentaires. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Que utilisez-vous pour le répertoire <br>synchronisation actuelle |<input type="checkbox">Aucune synchronisation (Cloud uniquement) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Connexion <br/> <input type="checkbox">Autre (à spécifier dans la <br>&nbsp;&nbsp; &nbsp;| |
> | L’identité fédérée est-elle déployée actuellement ? <br/>(Active Directory Federation Services ou <br>tierce partie) | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Si vous utilisez une identité fédérée, qu’est-ce que le <br>infrastructure de Fédération ? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Fédération tierce <br>&nbsp;&nbsp; &nbsp;passerelle <br>&nbsp;&nbsp; (Notez les détails &nbsp;dans la <br>&nbsp;&nbsp; &nbsp; | |
> | Si vous conservez actuellement un 365 Office actif <br>locataire est le domaine SMTP/SIP de votre <br>utilisateurs ciblés associés au client ? | <input type="checkbox">Non applicable : aucun bureau 365 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Non, SMTP/SIP de l’utilisateur <br>&nbsp;&nbsp; le domaine n’est &nbsp;pas associé <br>&nbsp;&nbsp; &nbsp;clients dans <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Oui, le protocole SMTP/SIP de l’utilisateur <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; | |
> | Les utilisateurs UPN correspondent-ils à leur adresse SMTP principale ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun <br/> <input type="checkbox">Manière incohérente | |

## <a name="existing-collaboration-platform-summary"></a>Résumé de la plateforme de collaboration existante

Utilisez le tableau suivant pour capturer des informations sur votre déploiement de plateforme de collaboration existant.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Microsoft Teams est-il déployé ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Skype Entreprise est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous que <br>Notez la version et la mise à jour cumulative (CU) <br>détails dans la colonne commentaires. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, en local <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Oui, hébergée et dédiée <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Oui, hébergée et partagée (tierce partie) <br/> <input type="checkbox">Non, autres | |
> | Exchange est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous que <br>Notez les détails de la version et de la CU dans les commentaires. <br>contrôle. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, en local <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Oui, hébergée et dédiée <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Oui, hébergée, partagée <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Non, autres | |
> | SharePoint est-il déployé ? <br/>Pour les déploiements locaux et hybrides, assurez-vous que <br>Notez les détails de la version et de la CU dans les commentaires. <br>contrôle. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, en local <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Oui, hébergée et dédiée <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Oui, hébergée, partagée <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Non, autres | |
> | Est-ce que le déploiement d’Office 365 OneDrive entreprise ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Avez-vous d’autres plates-formes tierces déployées <br>et en utilisation aujourd’hui ? Si tel est le cas, notez le nombre d’utilisateurs de <br>ces plateformes et les détails d’utilisation dans les commentaires <br>contrôle. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Marge <br/> <input type="checkbox">Autre (à spécifier dans les commentaires <br>&nbsp;&nbsp; &nbsp; | Nombre d’utilisateurs : <br/>Taille|
> | Vous envisagez de déplacer les utilisateurs du tiers <br>plates-formes | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Qu’est-ce que la solution de téléphonie et de conférence actuelle <br>Quels sont les utilisateurs dans le cadre de cette initiative ? | | |
> | Avez-vous des applications [SBCS prenant en charge le routage direct](direct-routing-plan.md#supported-session-border-controllers-sbcs) déployé pour vos bureaux dans le cadre de cette initiative ? <br>Si oui, notez les détails dans la colonne commentaires.| <input type="checkbox">Positive <br/> <input type="checkbox">Aucun ||

## <a name="collaboration-platform-deployment-details"></a>Détails du déploiement de la plateforme de collaboration

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (le cas échéant)

Le cas échéant, capturez les détails du déploiement de votre équipe à l’aide de l’exemple de table ci-dessous. Si vous n’avez pas déployé Teams, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Pour quels types d’utilisateurs Teams est-il activé ? | <input type="checkbox">Tous les utilisateurs de l’Organisation <br/> <input type="checkbox">Utilisateurs/groupes d’utilisateurs spécifiques <br>&nbsp;&nbsp; (À spécifier dans la colonne &nbsp;commentaires) ||
> | Quelles sont les fonctionnalités et les modalités des équipes utilisées ? | <input type="checkbox">Conversations basées sur les canaux <br/> <input type="checkbox">Conversation privée <br/> <input type="checkbox">Accès invité <br/> <input type="checkbox">Réunions de canal <br/> <input type="checkbox">Réunions privées <br/> <input type="checkbox">Appels privés <br/> <input type="checkbox">Meetup de canal ad hoc <br/> <input type="checkbox">Vidéos dans les réunions <br/> <input type="checkbox">Partage d’écran dans les réunions <br/> <input type="checkbox">Audioconférence <br/><input type="checkbox">Applications (applications)<br> &nbsp;&nbsp; &nbsp; Onglets <input type="checkbox"><br>&nbsp;&nbsp; Robots &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; Connecteurs &nbsp; <input type="checkbox"><br><input type="checkbox">Intégration de stockage cloud personnalisé <br>&nbsp;&nbsp; (Box, Dropbox, ShareFile, Google &nbsp; Drive) <br/> <input type="checkbox">Intégration de la messagerie électronique au canal <br/> <input type="checkbox">Autre (à spécifier dans la colonne commentaires.) | |
> | Quelles applications avez-vous déployées dans teams ? | | |
> | Avez-vous spécifiquement bloqué des fonctionnalités de Teams ? <br/>Si oui, notez les détails dans la colonne commentaires. | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun ||
> | Quels sont les clients Teams utilisés ? | <input type="checkbox">Sites <br/> <input type="checkbox">Windows <br/> <input type="checkbox">MacOS <br/> <input type="checkbox">Sorties <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | Quelles sont les personnes autorisées à créer des équipes ? | <input type="checkbox">Tout le monde au sein de l’Organisation <br>&nbsp;&nbsp; (Il s’agit du paramètre par &nbsp;défaut) <br/> <input type="checkbox">Personnes spécifiques <br>&nbsp;&nbsp; (À spécifier dans la colonne commentaires &nbsp;.) | |
> | Utilisez-vous les fonctionnalités de sécurité et conformité dans Teams ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Entreprise Online (le cas échéant)

Le cas échéant, capturez les détails de votre déploiement de Skype entreprise Online en utilisant l’exemple de tableau ci-dessous. Si vous n’avez pas déployé le déploiement de Skype entreprise Online, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quels sont les types d’utilisateurs activés pour Skype ? <br>pour Business Online ? | <input type="checkbox">Tous les utilisateurs de l’Organisation <br/> <input type="checkbox">Utilisateurs/groupes d’utilisateurs spécifiques <br>&nbsp;&nbsp; (À spécifier dans la colonne &nbsp;commentaires) | |
> | Les modalités et les fonctionnalités actuellement <br>vous utilisez aujourd’hui ? | <input type="checkbox">Messagerie instantanée et présence (mi)<br/> <input type="checkbox">Entretiens <br/> <input type="checkbox">Fédérés <br/> <input type="checkbox">Enregistrement de la réunion <br/> <input type="checkbox">Audioconférence Microsoft <br/> <input type="checkbox">Audioconférence tierce <br>&nbsp;&nbsp; (Notez les détails dans la colonne commentaires &nbsp;.) <br/> <input type="checkbox">Forfaits d’appels (auparavant appel RTC) <br/> <input type="checkbox">Standards automatiques de l’Organisation <br/> <input type="checkbox">Files d’attente d’appels | |
> | Avez-vous particulièrement bloqué tous les utilisateurs de Skype <br>Fonctionnalités de Business Online ? <br>Si oui, notez les détails dans la colonne commentaires. | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Quelle méthode utilisez-vous ou envisagez d’utiliser pour <br>connecter le système téléphonique (auparavant PBX Cloud) à <br>le RTC ? <br/>Sélectionnez toutes les réponses qui s’appliquent. | <input type="checkbox">Forfaits d’appels (auparavant appel RTC) <br/> <input type="checkbox">Connectivité PSTN locale (en tirant parti de la fonction existante <br>&nbsp;&nbsp; Skype entreprise 2015 ou Lync &nbsp;Server 2013 <br>&nbsp;&nbsp; &nbsp;déploiement) <br/> <input type="checkbox">Connectivité PSTN locale (via Cloud Connector) | |
> | Avez-vous transféré des numéros de téléphone vers Microsoft ? <br/>S’appliquent aux offres d’appels et aux appels audio. <br>Fonctionnalités de conférence. | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype entreprise local (le cas échéant)

Le cas échéant, capturez les détails du déploiement de Skype entreprise à l’aide de l’exemple de table ci-dessous. Si vous n’avez pas déployé Skype entreprise sur site, ignorez cette section.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quelles sont les versions de Lync ou Skype entreprise actuellement <br>le déploiement local est-il activé ? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype entreprise Server 2015 <br/> <input type="checkbox">Skype entreprise Server 2019 <br/> <input type="checkbox">Skype entreprise version Cloud Connector | |
> | La connectivité hybride avec Skype Entreprise Online est-elle configurée ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Cet environnement est-il hébergé et géré par un tiers ? <br/>Si oui, notez les détails dans la colonne commentaires. | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Les modalités et les fonctionnalités actuellement utilisées <br>celle? | <input type="checkbox">Messagerie instantanée et présence (mi) <br/> <input type="checkbox">Entretiens <br/> <input type="checkbox">Fédérés <br/> <input type="checkbox">Enregistrement de la réunion <br/> <input type="checkbox">Conversation permanente/conversation de groupe <br/> <input type="checkbox">Audioconférence Microsoft <br>&nbsp;&nbsp; (auparavant Conférence rendez-vous) &nbsp;sur votre <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Audioconférence tierce <br>&nbsp;&nbsp; (Notez les détails dans la colonne &nbsp;commentaires) <br/> <input type="checkbox">Voix entreprise avec RTC sur site <br>&nbsp;&nbsp; &nbsp;connectivité <br/> <input type="checkbox">Offres d’appels (anciennement PSTN Calling) via <br>&nbsp;&nbsp; &nbsp;entreprise Online | |
> | Quelle(s) version(s) du serveur Edge avez-vous déployé ? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype entreprise Server 2015 <br/> <input type="checkbox">Skype entreprise Server 2019 | |
> | Avez-vous déjà déployé Lync ou Skype entreprise Edge ? <br>au plus d’un centre de. <br/>Si oui, notez les détails dans la colonne commentaires. | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Sélectionnez les services que votre rôle Edge fournit aujourd’hui. | <input type="checkbox">Accès des utilisateurs externes (utilisateurs d’entreprise) <br/> <input type="checkbox">Accès des utilisateurs distants (externe anonyme <br>&nbsp;&nbsp; &nbsp;réunion) <br/> <input type="checkbox">Fédérés <br/> <input type="checkbox">Relais multimédia | |
> | Parmi les fonctions d’appel vocal suivantes <br>les dépendances sont actuellement activées ? <br/>Notez toute dépendance supplémentaire dans les commentaires. <br>contrôle. | <input type="checkbox">Options occupées <br/> <input type="checkbox">Parc d’appels <br/> <input type="checkbox">Prélèvement d’appel ou appel de groupe <br/> <input type="checkbox">Téléphones de surface courants ou « bureau à chaud » <br/> <input type="checkbox">Groupes de réponse ou groupes de recherche <br/> <input type="checkbox">Apparence de ligne partagée <br/> <input type="checkbox">Ligne privée <br/> <input type="checkbox">La boîte vocale <br/> <input type="checkbox">Appel via le Bureau <br/> <input type="checkbox">Numéros d’urgence ou d’information <br>&nbsp;&nbsp; (911, 811, &nbsp;411) <br/> <input type="checkbox">Numéro de téléphone <br/> <input type="checkbox">Standard automatique <br/> <input type="checkbox">Accès abonné <br/> <input type="checkbox">Appareils analogiques <br/> <input type="checkbox">DelrinaFax <br/> <input type="checkbox">Masquage ou modification de l’identification de l’appelant <br/> <input type="checkbox">Routage basé sur l’emplacement <br/> <input type="checkbox">Routage de moindre coût <br/> <input type="checkbox">Téléphones pour ascenseurs | |

## <a name="networking-and-access-to-office-365-services"></a>Mise en réseau et accès aux services 365 Office

Le tableau suivant vous permet de capturer les informations de mise en réseau de votre organisation et la manière dont vos utilisateurs sont connectés aux services Office 365.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Comment (ou comment) les utilisateurs dans le cadre de la migration <br>accéder aux équipes lorsqu’elles sont au bureau ? <br/>Sélectionnez toutes les réponses qui s’appliquent. | <input type="checkbox">Connexion NAT routée <br/> <input type="checkbox">Serveur proxy <br/> <input type="checkbox">Wi-Fi public <br/> <input type="checkbox">Wi-Fi géré (non public) <br/> <input type="checkbox">ExpressRoute (homologation Microsoft) ||
> | Si l’accès à Office 365 est par le biais d’un serveur proxy, y figure-il <br>tout moyen d’ignorer le proxy ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | ExpressRoute est-il utilisé actuellement ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun <br/> <input type="checkbox">Non, mais elle est planifiée | |
> | Avez-vous effectué une évaluation de la disponibilité du réseau ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Les utilisateurs doivent-ils utiliser un réseau VPN lors de la connexion à <br>ressources d’entreprise distantes ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | En cas d’utilisation d’un réseau privé virtuel (VPN), le trafic des équipes est-il exclu de <br>le VPN pour accéder directement aux services 365 d’Office ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Votre réseau prend-il en charge QoS ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Est-il possible de hiérarchiser le trafic audio et vidéo des équipes <br>pour une qualité d’une qualité optimale ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Tous les emplacements au sein d’une région sont-ils distants d’Internet, <br>est-ce que la sortie Internet est centralisée pour toute la région ? | <input type="checkbox">Accès régional à Internet <br/> <input type="checkbox">Accès centralisé à Internet | |

## <a name="endpoints"></a>Points de terminaison

Utilisez le tableau suivant pour capturer les détails des clients et des points de terminaison utilisés.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quel système d’exploitation de bureau les utilisateurs utilisent-ils ? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (spécifier la version dans la colonne commentaires.) <br/> <input type="checkbox">Linux (spécifiez la distribution dans la colonne commentaires.) <br/> <input type="checkbox">Autre (Notez les détails dans la colonne commentaires.) | |
> | Version de Microsoft Office déployée <br>sur ces appareils ? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office pour Mac 2011 <br/> <input type="checkbox">Office pour Mac 2016 <br/> <input type="checkbox">Autre (Notez les détails dans la colonne commentaires.) | |
> | Technologie de déploiement d’Office utilisée <br>dans votre organisation ? | <input type="checkbox">PORTION <br/> <input type="checkbox">Démarrer en un clic | |
> | Quels sont les appareils mobiles autorisés et pris en charge ? <br>plates-formes utilisées ? <br/>Sélectionnez toutes les réponses qui s’appliquent. | <input type="checkbox">Windows <br/> <input type="checkbox">Made <br/> <input type="checkbox">Sorties <br/> <input type="checkbox">Android <br/> <input type="checkbox">Autre (Notez les détails dans la colonne commentaires.) | |
> | Comment les appareils mobiles sont-ils fournis ? <br/>Sélectionnez toutes les réponses qui s’appliquent. | <input type="checkbox">Appareils d’entreprise <br/> <input type="checkbox">Mettre votre propre appareil | |
> | Quels appareils permettent aux utilisateurs d’accéder actuellement <br>services vocaux et de conférence <br>(combinés, casques, téléphones, vidéo) | | |

## <a name="operations"></a>Opérations

Utilisez le tableau suivant pour capturer les détails des aspects opérationnels de votre environnement.

> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quel est le modèle d’opérations de votre serveur Lync ? <br>Déploiement de Skype entreprise Server ou Office 365 <br>celle? | | |
> | Pouvez-vous présenter le contrat de support actuel pour <br>Lync Server, Skype entreprise Server ou Office 365 | | |
> | Si vous effectuez le déploiement dans plusieurs pays ou régions, <br>chaque pays/région dispose-t-il de sa propre application/téléphonie <br>le personnel est en charge de la gestion des tâches, ou cette gestion est-elle centralisée ? | <input type="checkbox">Opérations régionales et assistance <br/> <input type="checkbox">Opérations centralisées et prise en charge | |
> | Avez-vous suivi la [méthode de qualité d’appel](quality-of-experience-review-guide.md)? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun | |
> | Vous avez affecté une personne ou une équipe à <br>Rôle de défenseur de qualité pour la plateforme de collaboration <br>en cours d’utilisation ? | <input type="checkbox">Positive <br/> <input type="checkbox">Aucun ||
> | Comment surveiller votre serveur Lync, Skype pour <br>Déploiement d’Business Server ou d’Office 365 | | |
> | Avez-vous des problèmes de qualité des appels ? | <input type="checkbox">Positive<br/> <input type="checkbox">Aucun | |
> | Comment et quand devez-vous proposer une formation sur votre <br>support technique pour les nouveaux services et les nouvelles fonctionnalités ? | | |

## <a name="adoption-and-readiness"></a>Adoption et préparation

Utilisez le tableau suivant et consignez l’état d’adoption et de préparation actuel de votre organisation.

>
> | Question | Réponse | Commentaires |
> |---|---|---|
> | Quelle est votre utilisation actuellement active de <br>Skype entreprise ? | **_ _** % total des utilisateurs actifs par rapport aux utilisateurs activés | |
> | Utilisation de votre organisation <br>Skype entreprise ? | Conversations en tête-à-tête <br>&nbsp;&nbsp; &nbsp; Messagerie <input type="checkbox"> instantanée <br>&nbsp;&nbsp; Appel &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; Partage &nbsp; <input type="checkbox"><br> Meetings <br>&nbsp;&nbsp; &nbsp; Conférences <input type="checkbox"> téléphoniques<br>&nbsp;&nbsp; Partage &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; Appel &nbsp; <input type="checkbox"> | |
> | Votre organisation a-t-elle adopté un utilisateur <br>et équipe de gestion des changements ? | <input type="checkbox">Positive<br/> <input type="checkbox">Aucun | |
> | Comment évaluez-vous actuellement la réussite de la technologie <br>des déploiements tels que Skype entreprise ? | | |
> | Quel pourcentage de votre base de données d’utilisateurs avez-vous dit ? <br>avez-vous adopté Skype entreprise ? | | |
> | Quelle est l’opinion des utilisateurs concernant Skype Entreprise ? | <input type="checkbox">Pratique <br/> <input type="checkbox">Neutralisant <br/> <input type="checkbox">Habitude | |
> | Parmi les affirmations suivantes, laquelle décrit le mieux le déploiement <br>stratégie utilisée pour Skype entreprise <br>développement? | <input type="checkbox">Portée large : campagne par courrier électronique avec <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Étendu : portée élargie et variété <br>&nbsp;&nbsp; des campagnes de sensibilisation (posters &nbsp;, <br>&nbsp;&nbsp; &nbsp;et formation <br>&nbsp;&nbsp; (vidéos, guides d’utilisation, en &nbsp;personne) <br/> <input type="checkbox">Personnalisé : développé, et ciblé <br>&nbsp;&nbsp; &nbsp;par personnage <br/> <input type="checkbox">Ailleurs <br>&nbsp;&nbsp; (Notez les détails dans la colonne commentaires &nbsp;.) | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Point de décision</td><td><ul><li>Qui sera chargé d’effectuer une évaluation de l’environnement ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Étape suivante</td><td><ul><li>Documentez les résultats de l’évaluation de l’environnement.</li></ul></td></tr>
</table>

Après avoir évalué votre environnement, passez à l’étape suivante : [préparer votre réseau](prepare-network.md).
