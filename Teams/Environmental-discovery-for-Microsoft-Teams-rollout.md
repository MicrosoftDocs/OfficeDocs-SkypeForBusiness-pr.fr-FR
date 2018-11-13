---
title: Découverte de l’environnement pour un déploiement Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Découvrez comment effectuer une découverte environnementale détaillée lorsque vous planifiez votre parcours de Skype pour les entreprises à Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53f8704daf923b54e30d0061669ea1de63eeb02e
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295590"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Découverte de l’environnement pour un déploiement Microsoft Teams
===================================================

Détection est une des étapes première, clés que vous prendre lors de la planification de votre voyage pour Teams Microsoft.

Effectuer une découverte détaillée de votre environnement afin de mieux comprendre l’état actuel et de révéler des difficultés ou — encore plus — BLOQUEURS possibles à l’exécution de votre déploiement d’équipes.

<a name="discovery-questionnaire"></a>Questionnaire de découverte
=======================

Questionnaire exemples ci-dessous vous guide dans une série de questions pour vérifier que votre organisation est prête pour le déploiement réussi de système téléphonique et de conférence Audio avec des Plans de l’appel de fonctionnalités dans les équipes.

Toutes les questions relatives à votre existant infrastructure de collaboration et client Office 365, réseau, systèmes d’extrémité, opérations et d’adoption et de préparation sont incluses dans le cadre du questionnaire de découverte de l’environnement.

Le questionnaire est divisé en plusieurs sections pour confirmer la disponibilité de votre organisation pour votre déploiement d’équipes dans différentes zones principales. Travailler avec votre équipe de projet pour fournir les informations demandées avec autant de détails que possible pour faciliter vos activités de planification.

> [!TIP]
> Vous pouvez démarrer en copiant le questionnaire dans un document Microsoft Word. Essayez de répondre à toutes les questions et capturer tous les détails lorsque vous passez par le biais de.

<a name="project-team"></a>Équipe de projet
------------

Capture des informations détaillées sur les principales parties prenantes de votre projet de déploiement des équipes. Notez que cette personne peut jouer plusieurs rôles dans le projet.

> | Rôle                                  | Nom, adresse de messagerie, le numéro de téléphone | Emplacement, fuseau horaire | Commentaires      |
> |---------------------------------------|-----------------------------------|---------------------|---------------|
> | Sponsor exécutif                     |                                   |                     |               |
> | Chef de projet                          |                                   |                     |               |
> | Chef/architecte de la collaboration          |                                   |                     |               |
> | Consultant                            |                                   |                     |               |
> | Gestionnaire de projets                       |                                   |                     |               |
> | Spécialiste en gestion des changements/adoption |                                   |                     |               |
> | Directeur de réseau                          |                                   |                     |               |
> | Directeur de la sécurité                         |                                   |                     |               |
> | Directeur de la téléphonie                        |                                   |                     |               |
> | Directeur de bureau                          |                                   |                     |               |
> | Responsable du support                |                                   |                     |               |
> | Directeur du déploiement                       |                                   |                     |               |
> | Propriétaire de service                         |                                   |                     |               |
> | Responsable des sites                       |                                   |                     |               |
> | Responsable de l’équipe vidéo                       |                                   |                     |               |
> | Responsables de divisions                   |                                   |                     |               |

<a name="office-365-tenant-details"></a>Détails du client Office 365
-------------------------

Il est vivement recommandé d’avoir un client Office 365 actif lorsque vous travaillez avec ce questionnaire. Si vous n’avez pas activé, ou encore configuré un client Office 365, voir [planifier votre installation d’Office 365 pour entreprises](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Utilisez le tableau suivant pour capturer les informations sur le client Office 365.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Notez le client de production Office 365 <br>nom et l’ID de la colonne de réponse <br/>Si vous disposez de plusieurs clients <br>associé à votre organisation, <br>Notez tous les codes.  | Nom du client : <br/>ID de client :| |
> | Dans les régions les locataires sont déployés ?| | |
> | Sont ces clients pouvant être partagée de Office 365 ou <br>Dédié ? | <input type="checkbox">Pouvant être partagée<br/> <input type="checkbox">Dédiée | |
> | Quels sont les produits Microsoft Online utilisés actuellement ? <br/>Notez le nombre d’utilisateurs activés pour chacun <br>service dans la colonne commentaires. | <input type="checkbox">Équipes Microsoft <br/> <input type="checkbox">Skype pour les entreprises <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive entreprise <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Autres|                                   |
> | Quel niveau de la licence est activé pour Skype pour <br>Utilisateurs professionnels en ligne ? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E5 E4/G4 | Le nombre d’utilisateurs <br>pour chaque référence SKU : |
> | Nouveautés de la forêt Active Directory actuelle <br>niveau fonctionnel dans l’environnement ? <br/>S’il existe plusieurs forêts, notez les détails <br>dans la colonne commentaires. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Ce que vous utilisez pour le répertoire <br>synchronisation aujourd'hui ? |<input type="checkbox">Pas de synchronisation (en nuage seulement) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Connecter <br/> <input type="checkbox">Autres (spécifier dans le <br>&nbsp;&nbsp; &nbsp;Colonne commentaires.)| |
> | L’identité fédérée est-elle déployée actuellement ? <br/>(Active Directory Federation Services ou <br>tiers) | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Si vous utilisez des identités fédérées, quel est le <br>infrastructure de fédération ? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Fédération de tiers <br>&nbsp;&nbsp; &nbsp;passerelle <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans le <br>&nbsp;&nbsp; &nbsp;Colonne commentaires.) | |
> | Si vous gérez actuellement un active Office 365 <br>des clients, est le domaine SMTP/SIP de votre <br>utilisateurs ciblés associés avec le client ? | <input type="checkbox">N/a – aucun Office 365 <br>&nbsp;&nbsp; &nbsp;client en place <br/> <input type="checkbox">Non, les SMTP/SIP utilisateurs <br>&nbsp;&nbsp; &nbsp;domaine n’est pas associé <br>&nbsp;&nbsp; &nbsp;avec les clients dans <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Oui, les SMTP/SIP utilisateurs <br>&nbsp;&nbsp; &nbsp;domaine est associé <br>&nbsp;&nbsp; &nbsp;avec un client existant <br>&nbsp;&nbsp; &nbsp;dans Office 365 | |
> | UPN de l’utilisateur correspondent à leur adresse SMTP principale ? | <input type="checkbox">Oui <br/> <input type="checkbox">No <br/> <input type="checkbox">Incohérente | |

<a name="existing-collaboration-platform-summary"></a>Synthèse de plateforme de collaboration existants
---------------------------------------

Utilisez le tableau suivant pour capturer les informations sur votre déploiement de plateforme de collaboration existant.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Microsoft Teams est-il déployé ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Skype Entreprise est-il déployé ? <br/>Sur site et hybride déploiements, assurez-vous que <br>vous notez la version et la mise à jour cumulative (CU) <br>plus d’informations dans la colonne commentaires. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, sur site <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Oui, hébergé, dédiée <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox">Oui, hébergé, partagé (tiers) <br/> <input type="checkbox">Aucune, autres | |
> | Exchange est-il déployé ? <br/>Sur site et hybride déploiements, assurez-vous que <br>vous notez la version et les détails CU dans les commentaires <br>colonne. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, sur site <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Oui, hébergé, dédiée <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox">Oui, hébergé, partagées <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox">Aucune, autres | |
> | SharePoint est-il déployé ? <br/>Sur site et hybride déploiements, assurez-vous que <br>vous notez la version et les détails CU dans les commentaires <br>colonne. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, sur site <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Oui, hébergé, dédiée <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox">Oui, hébergé, partagées <br>&nbsp;&nbsp; &nbsp;(tiers) <br/> <input type="checkbox">Aucune, autres | |
> | Est Office 365 OneDrive for Business déployé ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Avez-vous besoin de n’importe quel autres plateformes tierces déployés <br>et en cours d’utilisation aujourd'hui ? Dans ce cas, notez le nombre d’utilisateurs de <br>ces plateformes et les détails d’utilisation dans les commentaires <br>colonne. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Marge <br/> <input type="checkbox">Autre (Veuillez préciser les commentaires <br>&nbsp;&nbsp; &nbsp;colonne.) | Nombre d’utilisateurs : <br/>Plus d’informations :|
> | Avez-vous l’intention de déplacer les utilisateurs de ces tiers <br>plateformes aux équipes ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Quelle est la solution de conférence et de téléphonie actuelle <br>les utilisateurs qui sont dans la portée de cette initiative ? | | |
> | Avez-vous besoin de [SBC qui prennent en charge le routage Direct](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) déployé pour vos sites qui se trouvent dans la portée de cette initiative ? <br>Si Oui, notez les informations dans la colonne commentaires.| <input type="checkbox">Oui <br/> <input type="checkbox">No ||

<a name="collaboration-platform-deployment-details"></a>Détails de déploiement de plateforme de collaboration
-----------------------------------------

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (le cas échéant)

Le cas échéant, capture les détails de vos équipes de déploiement à l’aide de la table d’exemple ci-dessous. Si vous n’avez pas déployé les équipes, ignorez cette section.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Pour quels types d’utilisateurs Teams est-il activé ? | <input type="checkbox">Tous les utilisateurs dans l’organisation <br/> <input type="checkbox">Groupes d’utilisateurs/utilisateurs spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne commentaires) ||
> | Les fonctionnalités d’équipes et les modalités sont en cours d’utilisation ? | <input type="checkbox">Conversations basée sur le canal <br/> <input type="checkbox">Conversation privée <br/> <input type="checkbox">Accès invité <br/> <input type="checkbox">Réunions de canal <br/> <input type="checkbox">Réunions privées <br/> <input type="checkbox">Appel privé <br/> <input type="checkbox">Meetup du canal ad hoc <br/> <input type="checkbox">Vidéos de réunions <br/> <input type="checkbox">Partage des réunions de l’écran <br/> <input type="checkbox">Services d’audioconférence <br/><input type="checkbox">Applications (applications)<br> &nbsp;&nbsp; &nbsp; <input type="checkbox"> Onglets<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Robots <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Connecteurs<br><input type="checkbox">Intégration du stockage dans le nuage personnalisé <br>&nbsp;&nbsp; &nbsp; (Zone, échange, ShareFile, Google lecteur) <br/> <input type="checkbox">Intégration de messagerie de canal <br/> <input type="checkbox">Autre (spécifier dans la colonne de commentaires). | |
> | Quelles applications ont déployé aux équipes ? | | |
> | Avez-vous spécifiquement bloqué des fonctionnalités de Teams ? <br/>Si Oui, notez les informations dans la colonne commentaires. | <input type="checkbox">Oui <br/> <input type="checkbox">No ||
> | Quels sont les clients Teams utilisés ? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | Quelles sont les personnes autorisées à créer des équipes ? | <input type="checkbox">Tout le monde dans l’organisation <br>&nbsp;&nbsp; &nbsp;(Il s’agit du paramètre par défaut) <br/> <input type="checkbox">Personnes spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne de commentaires). | |
> | Utilisez-vous les fonctionnalités de sécurité et conformité dans Teams ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Entreprise Online (le cas échéant)

Le cas échéant, capturer les détails de votre Skype pour le déploiement d’entreprise en ligne à l’aide de la table d’exemple ci-dessous. Si vous n’avez pas déployé Skype pour le déploiement d’entreprise en ligne, ignorez cette section.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quels types d’utilisateurs sont activés pour Skype <br>pour les entreprises en ligne ? | <input type="checkbox">Tous les utilisateurs dans l’organisation <br/> <input type="checkbox">Groupes d’utilisateurs/utilisateurs spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne commentaires) | |
> | Quelles modalités et fonctionnalités sont actuellement <br>en cours d’utilisation aujourd'hui ? | <input type="checkbox">Messagerie instantanée et présence (messagerie instantanée/P)<br/> <input type="checkbox">Conférence <br/> <input type="checkbox">Fédération <br/> <input type="checkbox">Enregistrement de la réunion <br/> <input type="checkbox">Conférence Audio Microsoft <br/> <input type="checkbox">Services d’audioconférence tiers <br>&nbsp;&nbsp; &nbsp;(Notez les informations dans la colonne commentaires.) <br/> <input type="checkbox">Plans d’appel (anciennement PSTN appelant) <br/> <input type="checkbox">Standards automatiques d’organisation <br/> <input type="checkbox">Files d’attente des appels | |
> | Spécifiquement bloqués n’importe quel Skype pour <br>Les fonctionnalités en ligne ? <br>Si Oui, notez les informations dans la colonne commentaires. | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Quelle méthode sont vous utilisez ou envisagez d’utiliser pour <br>connecter le système téléphonique (anciennement Cloud PBX) à <br>le réseau RTC ? <br/>Sélectionnez toutes les cases qui s’appliquent. | <input type="checkbox">Plans d’appel (anciennement PSTN appelant) <br/> <input type="checkbox">Connectivité PSTN (exploitation existant sur site <br>&nbsp;&nbsp; &nbsp;Skype pour Business 2015 ou Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;déploiement) <br/> <input type="checkbox">Connectivité PSTN (à l’aide de nuage connecteur) locale | |
> | Avez-vous transféré des numéros de téléphone vers Microsoft ? <br/>Ceci s’applique aux Plans de l’appelant et l’Audio <br>Fonctionnalités de conférence. | <input type="checkbox">Oui <br/> <input type="checkbox">No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype pour les entreprises locales (le cas échéant)

Le cas échéant, capturer les détails de votre Skype pour le déploiement d’entreprise à l’aide de la table d’exemple ci-dessous. Si vous n’avez pas déployé Skype pour les professionnels sur site, ignorez cette section.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quelles versions de Lync ou Skype pour les entreprises actuellement <br>sont déployés en local ? | <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype pour Business Server 2015 <br/> <input type="checkbox">Skype pour Business Server 2019 <input type="checkbox"> Skype pour l’édition de connecteur Business Cloud | |
> | La connectivité hybride avec Skype Entreprise Online est-elle configurée ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Cet environnement est hébergé et géré par un tiers ? <br/>Si Oui, notez les informations dans la colonne commentaires. | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Quelles modalités et fonctionnalités sont actuellement en cours d’utilisation <br>Aujourd'hui ? | <input type="checkbox">Messagerie instantanée et présence (messagerie instantanée/P) <br/> <input type="checkbox">Conférence <br/> <input type="checkbox">Fédération <br/> <input type="checkbox">Enregistrement de la réunion <br/> <input type="checkbox">Conversation permanente / de la conversation de groupe <br/> <input type="checkbox">Conférence Audio Microsoft <br>&nbsp;&nbsp; &nbsp;(anciennement rendez-vous conférence) sur votre <br>&nbsp;&nbsp; &nbsp;Lync Server local ou <br>&nbsp;&nbsp; &nbsp;Skype pour le déploiement d’entreprise <br/> <input type="checkbox">Services d’audioconférence tiers <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans la colonne commentaires) <br/> <input type="checkbox">À l’aide de Enterprise Voice locale PSTN <br>&nbsp;&nbsp; &nbsp;connectivité <br/> <input type="checkbox">Plans d’appel (anciennement PSTN appel) via <br>&nbsp;&nbsp; &nbsp;Hybride avec Skype pour les entreprises en ligne | |
> | Quelle(s) version(s) du serveur Edge avez-vous déployé ? | <input type="checkbox">Office Communications Server 2007 « R1 » <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype pour Business Server 2015 <br/> <input type="checkbox">Skype pour Business Server 2019| |
> | Avez-vous Lync ou Skype pour Business Edge déployé <br>dans plusieurs centres de données ? <br/>Si Oui, notez les informations dans la colonne commentaires. | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Sélectionnez les services fournis par votre rôle Edge aujourd'hui. | <input type="checkbox">Accès des utilisateurs externes (utilisateurs d’entreprise) <br/> <input type="checkbox">Accès des utilisateurs distants (anonyme externe <br>&nbsp;&nbsp; &nbsp;participants à la réunion) <br/> <input type="checkbox">Fédération <br/> <input type="checkbox">Serveur relais multimédia | |
> | Que la voix suivante fonctionnalités d’appel vous faire <br>actuellement ont des dépendances ? <br/>Notez toutes les dépendances supplémentaires dans les commentaires <br>colonne. | <input type="checkbox">Options de disponibilité <br/> <input type="checkbox">Mise en garde d’appels <br/> <input type="checkbox">Ou d’appel ou de groupe ou d’appel <br/> <input type="checkbox">Téléphones de partie commune, ou « desking à chaud » <br/> <input type="checkbox">Groupes de réponses ou de groupes de recherche <br/> <input type="checkbox">Apparence de la ligne partagé <br/> <input type="checkbox">Ligne privée <br/> <input type="checkbox">Messagerie vocale <br/> <input type="checkbox">Appel via le bureau <br/> <input type="checkbox">Numéros d’urgence ou d’informations <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox">Numérotation d’extension <br/> <input type="checkbox">Standard automatique <br/> <input type="checkbox">Accès abonné <br/> <input type="checkbox">Périphériques analogiques <br/> <input type="checkbox">Télécopie <br/> <input type="checkbox">Masquage des ID de l’appelant ou la modification <br/> <input type="checkbox">Routage basé sur l’emplacement <br/> <input type="checkbox">Routage à moindre coût <br/> <input type="checkbox">Téléphones de présentation | |

<a name="networking-and-access-to-office-365-services"></a>Mise en réseau et accès aux services Office 365
--------------------------------------------

Utilisez le tableau suivant pour capturer les informations de mise en réseau de votre organisation et comment les utilisateurs (ou sera) connectés aux services Office 365.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Comment (ou comment) les utilisateurs dans la portée de la migration <br>accéder aux équipes lorsqu’ils sont au bureau ? <br/>Sélectionnez toutes les cases qui s’appliquent. | <input type="checkbox">Connexion NAT routée <br/> <input type="checkbox">Serveur proxy <br/> <input type="checkbox">Wi-Fi public <br/> <input type="checkbox">Gérées Wi-Fi (non public) <br/> <input type="checkbox">ExpressRoute (peering Microsoft) ||
> | Si l’accès à Office 365 est via un serveur proxy, existe-t-il <br>un moyen de contourner le serveur proxy ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | ExpressRoute est-il utilisé actuellement ? | <input type="checkbox">Oui <br/> <input type="checkbox">No <br/> <input type="checkbox">Non, mais il est planifiée | |
> | Vous avez effectué une évaluation de préparation du réseau ? <br/>Pour plus d’informations, voir [Évaluation de préparation de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness). | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Sont requis pour utiliser un VPN pour se connecter à des utilisateurs <br>ressources d’entreprise à distance ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Si un VPN est utilisé, le trafic des équipes d’exclure de <br>le réseau VPN pour accéder directement aux Services Office 365 ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Votre réseau prend-il en charge QoS ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Vous pouvez classer trafic audio et vidéo d’équipes <br>pour une expérience de haute qualité ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Tous les emplacements dans une région doivent-elles sortie internet, <br>ou est sortie internet centralisée pour l’ensemble de la région ? | <input type="checkbox">Régionaux accès à internet <br/> <input type="checkbox">Accès centralisé à internet | |

> [!TIP]
> Pour calculer la quantité de bande passante et autres conditions de réseau pour votre voix dans le nuage déploiement, en fonction de votre organisation plus d’informations et l’activité estimée, visitez le site [Réseau planificateur](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) dans [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).

<a name="endpoints"></a>Points de terminaison
---------

Utilisez le tableau suivant pour capturer les détails des clients et des points de terminaison en cours d’utilisation.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quel système d’exploitation de bureau les utilisateurs utilisent-ils ? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">10 Windows <br/> <input type="checkbox">Mac (spécifier la version dans la colonne de commentaires). <br/> <input type="checkbox">Autres (Notez les informations dans la colonne commentaires.) | |
> | Quelle version de Microsoft Office est déployée. <br>pour ces périphériques ? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office pour Mac 2011 <br/> <input type="checkbox">Office pour Mac 2016 <br/> <input type="checkbox">Autres (Notez les informations dans la colonne commentaires.) | |
> | La technologie de déploiement d’Office est en cours d’utilisation <br>dans votre organisation ? | <input type="checkbox">MSI <br/> <input type="checkbox">Click-to-Run | |
> | Que sont les autorisés et pris en charge mobile <br>plateformes en cours d’utilisation ? <br/>Sélectionnez toutes les cases qui s’appliquent. | <input type="checkbox">Windows <br/> <input type="checkbox"> Mobile <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Autres (Notez les informations dans la colonne commentaires.) | |
> | Comment les appareils mobiles sont-ils fournis ? <br/>Sélectionnez toutes les cases qui s’appliquent. | <input type="checkbox">Périphériques de l’entreprise <br/> <input type="checkbox">Mettre votre propre périphérique | |
> | Quels appareils faire les utilisateurs actuellement utilisés pour accéder à <br>services de voix et de conférence <br>(téléphones, casques, téléphones, vidéo) ? | | |

<a name="operations"></a>Opérations
----------

Utilisez le tableau suivant pour capturer les détails des aspects opérationnels de votre environnement.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quel est votre modèle opérations pour votre Lync Server, <br>Skype pour Business Server ou le déploiement d’Office 365 <br>Aujourd'hui ? | | |
> | Peut décrivent le mécanisme de prise en charge actuel <br>Lync Server, Skype pour Business Server ou Office 365 ? | | |
> | Si vous déployez à plusieurs pays ou régions, <br>chaque pays/région a son propre informatique / téléphonie <br>pour fonctionner avec le personnel ou s’il être gérée de manière centralisée ? | <input type="checkbox">Prise en charge et opérations régionales <br/> <input type="checkbox">Prise en charge et les opérations centralisées | |
> | Suivez-vous la méthodologie de qualité des appels ? | <input type="checkbox">Oui <br/> <input type="checkbox">No | |
> | Vous avez affecté une personne ou l’équipe à la <br>Rôle Champion de qualité pour la plateforme de collaboration <br>en cours d’utilisation ? | <input type="checkbox">Oui <br/> <input type="checkbox">No ||
> | Comment pour surveiller votre Lync Server, Skype pour <br>Business Server ou Office 365 déploiement ? | | |
> | Avez-vous des problèmes de qualité des appels ? | <input type="checkbox">Oui<br/> <input type="checkbox">No | |
> | Comment et quand vous fournissez une formation pour votre <br>support technique sur les fonctionnalités et les nouveaux services ? | | |

<a name="adoption-and-readiness"></a>Kit d’adoption et de préparation
----------------------

Utilisez le tableau suivant et consignez l’état d’adoption et de préparation actuel de votre organisation.

> 
> |                                                    Question                                                     |                                                                                                                                                                                                                                                                                      Réponse                                                                                                                                                                                                                                                                                      | Commentaires |
> |-----------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
> |                          Quel est votre utilisation active actuelle du <br>Skype pour les entreprises ?                           |                                                                                                                                                                                                                                                                 **__** % utilisateurs au total actif par rapport aux utilisateurs                                                                                                                                                                                                                                                                 |          |
> |                             Comment votre organisation utilise <br>Skype pour les entreprises ?                              |                                                                                                   Conversations en tête-à-tête <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Par messagerie instantanée <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> L’appel <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> De partage<br> Réunions <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Conférence<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> De partage<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> L’appel                                                                                                   |          |
> |                   Votre entreprise possède-t-elle une Adoption utilisateur <br>et l’équipe de gestion des modifications ?                   |                                                                                                                                                                                                                                                           <input type="checkbox">Oui<br/> <input type="checkbox">No                                                                                                                                                                                                                                                            |          |
> |            Comment mesurer actuellement la réussite de la technologie <br>déploiements comme Skype pour les entreprises ?            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |          |
> |               Quel pourcentage de votre base d’utilisateurs diriez-vous a <br>adopté Skype pour les entreprises ?               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |          |
> |                                Quelle est l’opinion des utilisateurs concernant Skype Entreprise ?                                |                                                                                                                                                                                                                                       <input type="checkbox">Une bonne <br/> <input type="checkbox">Neutre <br/> <input type="checkbox">Incorrecte                                                                                                                                                                                                                                       |          |
> | Décrivant le mieux le déploiement <br>stratégie utilisée pour votre Skype pour les entreprises <br>déploiement ? | <input type="checkbox">Accès large : campagne Email avec <br>&nbsp;&nbsp; &nbsp;liens à la formation <br/> <input type="checkbox">Étendue : Accès large ainsi qu’une variété <br>&nbsp;&nbsp; &nbsp;de sensibilisation (affiches, <br>&nbsp;&nbsp; &nbsp;événements, les champions) et de formation <br>&nbsp;&nbsp; &nbsp;(vidéos, guides de l’utilisateur, en personne) <br/> <input type="checkbox">Adaptées : Une étendue plus ciblés <br>&nbsp;&nbsp; &nbsp;de messagerie et de formation par personnage <br/> <input type="checkbox">Autres <br>&nbsp;&nbsp; &nbsp;(Notez les informations dans la colonne commentaires.) |          |
