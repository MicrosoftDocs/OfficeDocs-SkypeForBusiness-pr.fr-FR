---
title: Découverte de l’environnement pour un déploiement de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Comment effectuer une découverte détaillée de l’environnement lors de la planification de votre voyage de Skype pour les entreprises à Teams de Microsoft.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5fde916c4fe9ece9ad80ec63dad1618fa0d1ae5
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Découverte de l’environnement pour un déploiement de Microsoft Teams
===================================================

La découverte est l’une des étapes très tout d’abord, clés que vous prenez lors de la planification de votre voyage à Teams de Microsoft.

Vous effectuez une découverte détaillée de votre environnement pour mieux comprendre l’état actuel et de révéler des difficultés ou, encore plus — BLOQUEURS possibles pour l’exécution de votre déploiement d’équipes.

<a name="discovery-questionnaire"></a>Questionnaire de découverte
=======================

Le questionnaire d’exemple ci-dessous vous guide tout au long une série de questions pour confirmer que votre organisation est prête pour le déploiement réussi d’audioconférence et système téléphonique avec les Plans d’appel de fonctions dans des équipes.

Toutes les questions relatives à votre existant infrastructure de collaboration et les clients Office 365, mise en réseau, points de terminaison, opérations et adoption et préparation sont incluses dans le cadre du questionnaire de découverte de l’environnement.

Le questionnaire est divisé en plusieurs sections pour confirmer est prête votre organisation pour le déploiement des équipes dans plusieurs zones principales. Travailler avec votre équipe de projet pour fournir les informations demandées avec autant de détails que possible afin de faciliter vos activités de planification.

> [!TIP]
> Vous pouvez démarrer en copiant le questionnaire dans un document Microsoft Word. Essayez de répondre à toutes les questions et de capturer tous les détails tandis que vous parcourez.

<a name="project-team"></a>Équipe de projet
------------

Capture des informations détaillées sur les parties prenantes clés de votre projet de déploiement d’équipes. Notez qu’une seule personne peut jouer plusieurs rôles tout au long du projet.

> | Rôle                                  | Nom, adresse, numéro de téléphone | Emplacement, fuseau horaire | Commentaires      |
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
> | Prospects de divisions                   |                                   |                     |               |

<a name="office-365-tenant-details"></a>Détails des clients Office 365
-------------------------

Il est vivement recommandé d’avoir un client Office 365 active pendant que vous travaillez avec ce questionnaire. Si vous n’avez pas activé ou encore configuré un client Office 365, reportez-vous à la section [planifier votre installation d’Office 365 pour entreprises](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Le tableau suivant permet de capturer des informations sur les clients d’Office 365.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Notez le locataire production Office 365 <br>nom et l’ID de la colonne de réponse <br/>Si vous avez plusieurs clients <br>associés à votre organisation, <br>Notez tous les codes.  | Nom du client : <br/>ID de clients :| |
> | Dans quelles régions les locataires sont déployés ?| | |
> | Sont les locataires pouvant être partagée de Office 365 ou <br>Dédié ? | <input type="checkbox">Pouvant être partagée<br/> <input type="checkbox">Dédié | |
> | Quels sont les produits Microsoft Online utilisés actuellement ? <br/>Remarque le nombre d’utilisateurs activés pour chaque <br>service dans la colonne commentaires. | <input type="checkbox">Équipes Microsoft <br/> <input type="checkbox">Skype pour entreprise <br>&nbsp;&nbsp; &nbsp;En ligne <br/> <input type="checkbox">Exchange en ligne <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive pour les entreprises <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Autres|                                   |
> | Quel niveau de la licence est activée pour Skype pour <br>Utilisateurs professionnels en ligne ? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 | Le nombre d’utilisateurs <br>pour chaque point de stock : |
> | Quelle est la forêt Active Directory en cours <br>niveau fonctionnel dans l’environnement ? <br/>S’il existe plus d’une forêt, notez les détails <br>dans la colonne commentaires. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Ce que vous utilisez pour l’annuaire <br>synchronisation aujourd'hui ? |<input type="checkbox">Pas de synchronisation (cloud uniquement) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Connecter <br/> <input type="checkbox">Autres (spécifier dans la <br>&nbsp;&nbsp; &nbsp;Colonne commentaires.)| |
> | L’identité fédérée est-elle déployée actuellement ? <br/>(Active Directory Federation Services ou <br>tiers) | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Si vous utilisez des identités fédérées, quel est le <br>infrastructure de la fédération ? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Fédération de tiers <br>&nbsp;&nbsp; &nbsp;passerelle <br>&nbsp;&nbsp; &nbsp;(Notez les informations dans le <br>&nbsp;&nbsp; &nbsp;Colonne commentaires.) | |
> | Si vous utilisez actuellement un actif Office 365 <br>client, est le domaine SMTP/SIP de votre <br>les utilisateurs associés au locataire les cibles ? | <input type="checkbox">N – aucune Office 365 <br>&nbsp;&nbsp; &nbsp;clients en place <br/> <input type="checkbox">Non, les SMTP/SIP utilisateurs <br>&nbsp;&nbsp; &nbsp;domaine n’est pas associé <br>&nbsp;&nbsp; &nbsp;avec les locataires dans <br>&nbsp;&nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Oui, les SMTP/SIP utilisateurs <br>&nbsp;&nbsp; &nbsp;domaine est associé <br>&nbsp;&nbsp; &nbsp;avec un client existant <br>&nbsp;&nbsp; &nbsp;dans Office 365 | |
> | L’UPN de l’utilisateur correspondent à leur adresse SMTP principale ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° <br/> <input type="checkbox">Incohérente | |

<a name="existing-collaboration-platform-summary"></a>Plate-forme de collaboration résumé
---------------------------------------

Le tableau suivant permet de capturer des informations sur le déploiement de plate-forme de collaboration existant.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Microsoft Teams est-il déployé ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Skype Entreprise est-il déployé ? <br/>Pour les hybrides et les locaux les déploiements, assurez-vous que <br>Notez la version et la mise à jour cumulative (CU) <br>Détails de la colonne commentaires. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, sur site <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Oui, hébergé, dédiée <br>&nbsp;&nbsp; &nbsp;(tierce partie) <br/> <input type="checkbox">Oui, hébergé, partagé (tierce partie) <br/> <input type="checkbox">Non, autres | |
> | Exchange est-il déployé ? <br/>Pour les hybrides et les locaux les déploiements, assurez-vous que <br>Notez la version et la CU détails dans les commentaires <br>colonne. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, sur site <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Oui, hébergé, dédiée <br>&nbsp;&nbsp; &nbsp;(tierce partie) <br/> <input type="checkbox">Oui, hébergé, partagées <br>&nbsp;&nbsp; &nbsp;(tierce partie) <br/> <input type="checkbox">Non, autres | |
> | SharePoint est-il déployé ? <br/>Pour les hybrides et les locaux les déploiements, assurez-vous que <br>Notez la version et la CU détails dans les commentaires <br>colonne. | <input type="checkbox">Oui, Office 365 <br/> <input type="checkbox">Oui, hybride (avec Office 365) <br/> <input type="checkbox">Oui, sur site <br/> <input type="checkbox">Oui, en ligne, dédié <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Oui, hébergé, dédiée <br>&nbsp;&nbsp; &nbsp;(tierce partie) <br/> <input type="checkbox">Oui, hébergé, partagées <br>&nbsp;&nbsp; &nbsp;(tierce partie) <br/> <input type="checkbox">Non, autres | |
> | Est Office 365 OneDrive pour entreprise déployé ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Vous disposez de toutes les autres plates-formes de tiers déployés <br>et en cours d’utilisation dès aujourd'hui ? Dans ce cas, notez le nombre d’utilisateurs de <br>ces plates-formes et les détails de l’utilisation dans les commentaires <br>colonne. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Marge <br/> <input type="checkbox">Autres (à spécifier dans les commentaires <br>&nbsp;&nbsp; &nbsp;colonne.) | Nombre d’utilisateurs : <br/>Détails :|
> | Avez-vous l’intention de déplacer les utilisateurs de ces tiers <br>plates-formes aux équipes ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Quelle est la solution de conférence et de téléphonie en cours <br>les utilisateurs qui sont dans la portée de cette initiative ? | | |

<a name="collaboration-platform-deployment-details"></a>Détails de déploiement de plate-forme de collaboration
-----------------------------------------

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (le cas échéant)

Le cas échéant, capture les détails de vos équipes de déploiement à l’aide de la table d’exemple ci-dessous. Si vous n’avez pas déployé des équipes, ignorez cette section.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Pour quels types d’utilisateurs Teams est-il activé ? | <input type="checkbox">Tous les utilisateurs de l’organisation <br/> <input type="checkbox">Groupes d’utilisateurs/utilisateurs spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne commentaires) ||
> | Les fonctionnalités d’équipes et les modalités sont en cours d’utilisation ? | <input type="checkbox">Conversations à base de canal <br/> <input type="checkbox">Conversation privée <br/> <input type="checkbox">Accès invité <br/> <input type="checkbox">Réunions de canal <br/> <input type="checkbox">Conférences privées <br/> <input type="checkbox">Appel privé <br/> <input type="checkbox">Meetup du canal ad hoc <br/> <input type="checkbox">Vidéos de réunions <br/> <input type="checkbox">Partage des réunions de l’écran <br/> <input type="checkbox">Conférence audio <br/><input type="checkbox">Applications (applications)<br> &nbsp;&nbsp; &nbsp; <input type="checkbox"> Onglets<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Robots <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Liens<br><input type="checkbox">Intégration de stockage cloud personnalisé <br>&nbsp;&nbsp; &nbsp; (Zone, échange, ShareFile, lecteur de Google) <br/> <input type="checkbox">Intégration de messagerie électronique de canal <br/> <input type="checkbox">Autre (préciser dans la colonne commentaires.) | |
> | Quelles applications ont déployé aux équipes ? | | |
> | Avez-vous spécifiquement bloqué des fonctionnalités de Teams ? <br/>Si Oui, notez les informations dans la colonne commentaires. | <input type="checkbox">Oui <br/> <input type="checkbox">N° ||
> | Quels sont les clients Teams utilisés ? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">e/s <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | Quelles sont les personnes autorisées à créer des équipes ? | <input type="checkbox">Tout le monde dans l’organisation <br>&nbsp;&nbsp; &nbsp;(C’est le paramètre par défaut) <br/> <input type="checkbox">Personnes spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne commentaires.) | |
> | Utilisez-vous les fonctionnalités de sécurité et conformité dans Teams ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |

### <a name="skype-for-business-online-if-applicable"></a>Skype Entreprise Online (le cas échéant)

Le cas échéant, capturer les détails de votre Skype pour le déploiement d’entreprise en ligne à l’aide de la table d’exemple ci-dessous. Si vous n’avez pas déployé Skype pour le déploiement d’entreprise en ligne, ignorez cette section.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quels types d’utilisateurs sont activés pour Skype <br>pour les entreprises en ligne ? | <input type="checkbox">Tous les utilisateurs de l’organisation <br/> <input type="checkbox">Groupes d’utilisateurs/utilisateurs spécifiques <br>&nbsp;&nbsp; &nbsp;(Spécifier dans la colonne commentaires) | |
> | Les modalités et les fonctionnalités qui sont actuellement <br>en cours d’utilisation dès aujourd'hui ? | <input type="checkbox">La messagerie instantanée et présence (IM/P)<br/> <input type="checkbox">Conférence <br/> <input type="checkbox">Fédération <br/> <input type="checkbox">Enregistrement de la réunion <br/> <input type="checkbox">Conférences Audio Microsoft <br/> <input type="checkbox">Conférence audio de tiers <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans la colonne commentaires.) <br/> <input type="checkbox">Plans d’appel (anciennement RTPC appelant) <br/> <input type="checkbox">Surveillances automatiques d’organisation <br/> <input type="checkbox">Files d’attente de l’appel | |
> | Spécifiquement bloqués tout Skype pour <br>Des capacités en ligne ? <br>Si Oui, notez les informations dans la colonne commentaires. | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Quelle méthode sont automatiquement à l’aide ou le plan à utiliser pour <br>Connectez le système téléphonique (anciennement nuage PBX) à <br>RTC ? <br/>Sélectionnez toutes les réponses appropriées. | <input type="checkbox">Plans d’appel (anciennement RTPC appelant) <br/> <input type="checkbox">La connectivité RTPC (exploitant existant sur site <br>&nbsp;&nbsp; &nbsp;Skype pour entreprise 2015 ou Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;déploiement) <br/> <input type="checkbox">Connectivité RTPC local (à l’aide du connecteur de nuage) | |
> | Avez-vous transféré des numéros de téléphone vers Microsoft ? <br/>Ceci s’applique aux Plans de l’appelant et de l’Audio <br>Fonctionnalités de conférence. | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype pour entreprise sur site (si applicable)

Le cas échéant, capturer les détails de votre Skype pour le déploiement de l’entreprise à l’aide de la table d’exemple ci-dessous. Si vous n’avez pas déployé Skype pour professionnels sur site, ignorez cette section.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quelles sont les versions de Lync ou Skype pour entreprise actuellement <br>sont déployées sur site ? | <input type="checkbox">Office Communications Server 2007 « R1 » <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype pour Business Server 2015 <br/> <input type="checkbox">Skype pour connecteur de Cloud Business Edition | |
> | La connectivité hybride avec Skype Entreprise Online est-elle configurée ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Est-ce que cet environnement hébergé et géré par un tiers ? <br/>Si Oui, notez les informations dans la colonne commentaires. | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Les modalités et les fonctionnalités sont actuellement en cours d’utilisation <br>Aujourd'hui ? | <input type="checkbox">La messagerie instantanée et présence (IM/P) <br/> <input type="checkbox">Conférence <br/> <input type="checkbox">Fédération <br/> <input type="checkbox">Enregistrement de la réunion <br/> <input type="checkbox">Conversation permanente / groupe de conversation <br/> <input type="checkbox">Conférences Audio Microsoft <br>&nbsp;&nbsp; &nbsp;(anciennement composer de conférence) sur votre <br>&nbsp;&nbsp; &nbsp;Lync Server sur site ou <br>&nbsp;&nbsp; &nbsp;Skype pour le déploiement d’entreprise <br/> <input type="checkbox">Conférence audio de tiers <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans la colonne commentaires) <br/> <input type="checkbox">À l’aide de Voix Entreprise local RTC <br>&nbsp;&nbsp; &nbsp;connexion <br/> <input type="checkbox">Plans d’appel (anciennement RTPC appelant) via <br>&nbsp;&nbsp; &nbsp;Hybride avec Skype pour l’activité en ligne | |
> | Quelle(s) version(s) du serveur Edge avez-vous déployé ? | <input type="checkbox">Office Communications Server 2007 « R1 » <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype pour Business Server 2015 | |
> | Avez-vous Lync ou Skype pour avantage déployé <br>en plus d’un centre de données ? <br/>Si Oui, notez les informations dans la colonne commentaires. | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Sélectionnez les services que votre rôle Edge fournit aujourd'hui. | <input type="checkbox">Accès des utilisateurs externes (utilisateurs d’entreprise) <br/> <input type="checkbox">Accès des utilisateurs distants (anonyme externe <br>&nbsp;&nbsp; &nbsp;participants à la réunion) <br/> <input type="checkbox">Fédération <br/> <input type="checkbox">Relais multimédia | |
> | Que la voix suivante l’appel de fonctions de faire vous <br>actuellement ont des dépendances ? <br/>Notez les dépendances supplémentaires dans les commentaires <br>colonne. | <input type="checkbox">Options de disponibilité <br/> <input type="checkbox">Parc d’appel <br/> <input type="checkbox">Appel de remise en mains propres ou prise d’appel de groupe <br/> <input type="checkbox">Téléphone de zone commune, ou « hot desking » <br/> <input type="checkbox">Les groupes de réponse ou de groupes de recherche <br/> <input type="checkbox">Apparence de la ligne partagée <br/> <input type="checkbox">Ligne privée <br/> <input type="checkbox">Messagerie vocale <br/> <input type="checkbox">Appeler via le travail <br/> <input type="checkbox">Numéros d’urgence ou d’informations <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox">Numérotation d’extension <br/> <input type="checkbox">Standard automatique <br/> <input type="checkbox">Accès abonné <br/> <input type="checkbox">Périphériques analogiques <br/> <input type="checkbox">Télécopie <br/> <input type="checkbox">Masquage des ID de l’appelant ou de la modification <br/> <input type="checkbox">Routage basé sur l’emplacement <br/> <input type="checkbox">Le routage de moindre coût <br/> <input type="checkbox">Téléphones d’ascenseur | |

<a name="networking-and-access-to-office-365-services"></a>Mise en réseau et l’accès aux services Office 365
--------------------------------------------

Le tableau suivant permet de capturer des détails de mise en réseau de votre organisation et comment les utilisateurs (ou sera) connecté aux services d’Office 365.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Comment (ou quoi) les utilisateurs dans la portée de la migration <br>accéder aux équipes lorsqu’ils sont au bureau ? <br/>Sélectionnez toutes les réponses appropriées. | <input type="checkbox">Connexion routée de NAT <br/> <input type="checkbox">Serveur proxy <br/> <input type="checkbox">Wi-Fi public <br/> <input type="checkbox">Gérer le Wi-Fi (non publique) <br/> <input type="checkbox">ExpressRoute (homologation Microsoft) ||
> | Si l’accès à Office 365 est via un serveur proxy, existe-t-il <br>un moyen de contourner le serveur proxy ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | ExpressRoute est-il utilisé actuellement ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° <br/> <input type="checkbox">Non, mais il est en cours de planification | |
> | Vous avez effectué une évaluation de la disponibilité du réseau ? <br/>Pour plus d’informations, reportez-vous à la section [Évaluation de la disponibilité du réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness). | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Les utilisateurs doivent utiliser une connexion VPN lors de la connexion à <br>les ressources d’entreprise à distance ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Si un VPN est utilisé, le trafic des équipes d’exclure de <br>la connexion VPN pour accéder directement aux Services Office 365 ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Votre réseau prend-il en charge QoS ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Vous pouvez classer le trafic audio et vidéo équipes <br>pour une expérience de qualité ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Tous les emplacements au sein d’une région ont une sortie internet, <br>ou sortie d’internet centralisée pour l’ensemble de la région ? | <input type="checkbox">Accès à internet régional <br/> <input type="checkbox">Accès centralisé à internet | |

> [!TIP]
> Pour calculer la quantité de bande passante et les autres exigences de réseau pour votre voix de nuage déploiement, en fonction des détails et l’activité estimée, de votre organisation, reportez-vous au [Module de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) dans [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).

<a name="endpoints"></a>Points de terminaison
---------

Le tableau suivant permet de capturer les détails des clients et des points de terminaison en cours d’utilisation.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quel système d’exploitation de bureau les utilisateurs utilisent-ils ? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (spécifier la version dans la colonne commentaires.) <br/> <input type="checkbox">Autres (Notez les détails dans la colonne commentaires.) | |
> | Quelle version de Microsoft Office est déployée. <br>pour ces périphériques ? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office pour Mac 2011 <br/> <input type="checkbox">Office pour Mac 2016 <br/> <input type="checkbox">Autres (Notez les détails dans la colonne commentaires.) | |
> | La technologie de déploiement d’Office est en cours d’utilisation <br>dans votre organisation ? | <input type="checkbox">MSI <br/> <input type="checkbox">Démarrer en un clic | |
> | Que sont les autorisés et pris en charge mobile <br>plates-formes en cours d’utilisation ? <br/>Sélectionnez toutes les réponses appropriées. | <input type="checkbox">Windows <br/> <input type="checkbox"> Mobile <br/> <input type="checkbox">e/s <br/> <input type="checkbox">Android <br/> <input type="checkbox">Autres (Notez les détails dans la colonne commentaires.) | |
> | Comment les appareils mobiles sont-ils fournis ? <br/>Sélectionnez toutes les réponses appropriées. | <input type="checkbox">Périphériques de l’entreprise <br/> <input type="checkbox">Commercialisez votre propre périphérique | |
> | Quels périphériques faire les utilisateurs actuellement utilisé pour accéder à <br>services de conférence et de voix <br>(combinés, casques, téléphones, vidéo) ? | | |

<a name="operations"></a>Opérations
----------

Le tableau suivant permet de capturer les détails des aspects opérationnels de votre environnement.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quel est votre modèle d’opérations pour votre serveur Lync, <br>Skype pour Business Server ou le déploiement d’Office 365 <br>Aujourd'hui ? | | |
> | Peut présenter le mécanisme de prise en charge actuelle <br>Lync Server, Skype pour Business Server ou Office 365 ? | | |
> | Si vous déployez à plusieurs pays ou régions, <br>chaque pays possède ses propres informatique / téléphonie <br>pour travailler avec le personnel, ou s’il être gérée de manière centralisée ? | <input type="checkbox">Prise en charge et opérations régionales <br/> <input type="checkbox">Prise en charge et les opérations centralisées | |
> | Suivez-vous la méthodologie de qualité des appels ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° | |
> | Vous avez affecté une personne ou une équipe pour le <br>Rôle de Champion de qualité pour la plate-forme de collaboration <br>en cours d’utilisation ? | <input type="checkbox">Oui <br/> <input type="checkbox">N° ||
> | Comment pour surveiller votre serveur Lync, Skype pour <br>Business Server ou Office 365 déploiement ? | | |
> | Avez-vous des problèmes de qualité des appels ? | <input type="checkbox">Oui<br/> <input type="checkbox">N° | |
> | Comment et quand vous fournissez une formation pour votre <br>support technique sur les fonctionnalités et les nouveaux services ? | | |

<a name="adoption-and-readiness"></a>Préparation et adoption
----------------------

Utilisez le tableau suivant et consignez l’état d’adoption et de préparation actuel de votre organisation.

> | Question | Réponse | Commentaires |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quelle est votre utilisation actuelle active du <br>Skype pour les entreprises ? | ___ % total active des utilisateurs par rapport aux utilisateurs | |
> | Comment votre organisation utilise-t-elle <br>Skype pour les entreprises ? | Conversations en tête-à-tête <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> D’appel <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> De partage<br> Réunions <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Conférence<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> De partage<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> D’appel| |
> | Votre entreprise dispose-t-elle d’une Adoption d’utilisateur <br>et l’équipe de gestion des modifications ? | <input type="checkbox">Oui<br/> <input type="checkbox">N° | |
> | Comment pouvez-vous actuellement mesure du succès de la technologie <br>déploiements comme Skype pour les entreprises ? | | |
> | Quel pourcentage de votre base d’utilisateurs diriez-vous a <br>adopté Skype pour les entreprises ? | | |
> | Quelle est l’opinion des utilisateurs concernant Skype Entreprise ? | <input type="checkbox">Bonne <br/> <input type="checkbox">Neutre <br/> <input type="checkbox">Incorrect | |
> | Décrivant le mieux le déploiement <br>stratégie utilisée pour votre Skype pour entreprise <br>déploiement ? | <input type="checkbox">Accès large : campagne Email avec <br>&nbsp;&nbsp; &nbsp;des liens à la formation <br/> <input type="checkbox">Développée : Accès large ainsi qu’une variété <br>&nbsp;&nbsp; &nbsp;des campagnes de sensibilisation (affiches, <br>&nbsp;&nbsp; &nbsp;événements, champions) et de la formation <br>&nbsp;&nbsp; &nbsp;(vidéos, guides de l’utilisateur, de personne à personne) <br/> <input type="checkbox">Adaptées : De développé, plus ciblé <br>&nbsp;&nbsp; &nbsp;de messagerie et de la formation par un personnage <br/> <input type="checkbox">Autres <br>&nbsp;&nbsp; &nbsp;(Notez les détails dans la colonne commentaires.) | |