---
title: Planifier l’application Response Group dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planification de Response groups dans Skype entreprise Server Voice, qui vous permet de configurer le routage des appels vers des groupes d’utilisateurs. Cela inclut les conditions requises pour les fichiers audio.
ms.openlocfilehash: b1c8a2ab1a7dc42fd290df4bdc1ccf69b52db43a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276467"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Planifier l’application Response Group dans Skype entreprise Server

Planification de Response groups dans Skype entreprise Server Voice, qui vous permet de configurer le routage des appels vers des groupes d’utilisateurs. Cela inclut les conditions requises pour les fichiers audio.

Si votre organisation dispose de groupes de personnes qui répondent et gèrent certains types d’appels, par exemple pour le service clientèle, un support technique interne ou une assistance téléphonique générale pour un service, vous pouvez déployer l’application Response Group pour gérer ces types d’appels. L’application groupe de réponse achemine et met en file d’attente les appels entrants vers des personnes désignés comme agents. L’utilisation des groupes Response Group vous permet d’améliorer l’utilisation des services de support téléphonique et de réduire la charge liée à l’exécution de ces services.

Quand un appelant appelle un Response Group, l’appel est acheminé vers un agent en fonction du groupe de recherche ou des réponses de l’appelant aux questions du système de réponse vocale interactive. L’application Response Group utilise des méthodes de routage de groupe de réponse standard pour acheminer l’appel vers le prochain agent disponible. Parmi les méthodes de routage d’appel prises en charge figurent le routage de série, parallèle, le plus longuement inactif, tourniquet (round robin) et le nouveau routage Attendant (dans lequel tous les agents sont appelés en même temps pour tous les appels entrants, quelle que soit leur présence actuelle).

Si aucun agent n’est disponible, l’appel est mis en file d’attente jusqu’à ce qu’un agent se libère. Quand il est en file d’attente, l’appelant entend de la musique jusqu’à ce qu’un agent accepte l’appel. Si la file d’attente est pleine, ou si l’appel arrive à expiration dans la file d’attente, l’appelant entendra probablement un message, puis sera déconnecté ou transféré vers une autre destination. Quand un agent accepte l’appel, l’appelant peut dans certains cas voir l’identité de l’agent, selon la façon dont l’administrateur configure le groupe de réponses. Les agents peuvent être formels, c’est-à-dire qu’ils doivent se connecter au groupe avant de pouvoir accepter les appels y étant acheminés, ou informels, c’est-à-dire qu’ils n’ont pas besoin de se connecter ou déconnecter du groupe pour accepter les appels.

> [!NOTE]
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de local vers en ligne, les appels de groupe de réponse ne seront pas routés vers cet agent.

> [!NOTE]
> L’application Response Group utilise un service interne appelé faire correspondre pour mettre en file d’attente les appels et rechercher les agents disponibles. Chaque ordinateur qui exécute l’application Response Group exécute le service Matching, mais une seule correspondance pour le service par pool est active à la fois, les autres sont passives. En cas d’indisponibilité du service d’établissement des correspondances actif au cours d’une interruption de service imprévue, l’un des services passifs devient actif. L’application de groupe de réponse utilise le mieux pour s’assurer que le routage d’appel et la mise en file d’attente continuent de fonctionner sans interruption. Cependant, lorsqu’une transition du service d’établissement des correspondances se produit, tous les appels en transfert à ce moment-là sont perdus. Par exemple, si la transition est en raison du fait que le serveur frontal s’arrête, tout appel actuellement géré par le service de correspondance active sur le serveur principal est également perdu.

## <a name="response-group-workflows"></a>Flux de travail Response Group

Un flux de travail définit le comportement d’un appel, du déclenchement de la sonnerie du téléphone jusqu’au moment où une personne répond à l’appel. Le flux de travail spécifie la file d’attente à utiliser pour la mise en attente de l’appel et indique la méthode de routage à appliquer aux groupes de recherche ou les questions et les réponses à utiliser pour les groupes Response Group interactifs. Un flux de travail définit également des paramètres, comme un message d’accueil, l’attente musicale, les heures de bureau et les congés.

> [!NOTE]
> Vous devez créer des groupes d’agents et des files d’attente avant de créer un flux de travail qui les utilise.

## <a name="management-of-response-groups"></a>Gestion des groupes Response Group

Dans Skype entreprise Server, deux rôles de gestion sont disponibles pour gérer les groupes de réponse: responsable du groupe de réponse et administrateur du groupe de réponse. Les administrateurs de groupe de réponse peuvent gérer tout aspect de n’importe quel Response Group. Les responsables de groupe de réponse peuvent uniquement gérer certains aspects, et uniquement pour les groupes de réponse qu’ils possèdent. Le rôle responsable peut vous aider à réduire les coûts de votre administration, car vous pouvez déléguer des responsabilités limitées pour des groupes de réponse spécifiques à n’importe quel utilisateur qui est activé pour voix entreprise. Notez qu’un utilisateur peut être à la fois responsable du groupe de réponse et administrateur du groupe de réponse.

Pour prendre en charge le rôle de responsable, l’application Response Group utilise un **type de flux de travail** géré ou non géré. Le tableau ci-dessous décrit les groupes Response Group gérés et non gérés.

**Groupes Response Group gérés et non gérés**

|**Type de groupe Response Group**|**Description**|
|:-----|:-----|
|Non géré  <br/> | Aucun gestionnaire n’est affecté aux groupes Response Group non gérés. Seul l’administrateur du groupe de réponse peut configurer ces groupes de réponse. <br/>  Plusieurs groupes Response Group non gérés peuvent partager une file d’attente ou un groupe d’agents. <br/>  Lorsque vous migrez des groupes de réponse d’une version antérieure vers Skype entreprise Server, le type est défini sur non géré. <br/> |
|Géré  <br/> | Les administrateurs de groupe de réponse peuvent configurer n’importe quel aspect de groupes de réponse gérés. <br/>  Les responsables de groupe de réponse ne peuvent pas afficher ou modifier des groupes de réponse qui ne sont pas explicitement attribués. <br/>  Les responsables de groupe de réponse peuvent configurer uniquement certains paramètres des groupes de réponse qui leur sont explicitement affectés. <br/>  Les groupes Response Group gérés ne peuvent pas partager des files d’attente ou des groupes d’agents avec d’autres groupes Response Group, qu’ils soient gérés ou non gérés. <br/> |

Le tableau suivant décrit les actions que les responsables de groupe de réponse peuvent exécuter et ne peuvent pas effectuer pour les groupes de réponse qui leur sont attribués.

**Fonctions du gestionnaire Response Group**

|**Peut configurer :**|**Peut créer, supprimer ou configurer :**|**Ne peut pas :**|
|:-----|:-----|:-----|
| Agents <br/>  Message d’accueil <br/>  Nom du groupe de réponse <br/>  Description <br/>  Numéro affiché <br/>  Heures d’ouverture <br/>  Attente musicale <br/>  Statut (actif/inactif) <br/>  Flux de travail de groupe de recherche ou flux de travail de réponse vocale interactive (IVR) <br/> | Groupes d’agents <br/>  Files d’attente <br/>  Périodes de congé <br/> | Créer ou supprimer un type de flux de travail <br/>  Modifier les paramètres principaux des groupes Response Group, tels que : **URI SIP**, **Numéro de téléphone** ou **Type de flux de travail**  <br/> |

Les responsables de groupe de réponse peuvent utiliser les outils suivants pour gérer leurs groupes de réponse désignés.

- Panneau de configuration Skype entreprise Server

    > [!NOTE]
    > Les responsables de groupe de réponse peuvent uniquement gérer les paramètres de groupe de réponse à l’aide de cet outil. Les autres paramètres du serveur Skype entreprise ne sont pas disponibles pour les responsables.

- outil de configuration Response Group

- Skype Entreprise Server Management Shell

Response Group s’adapte bien aux environnements de services ou de groupe de travail (pour plus de détails, voir [planification de la capacité pour Response Group](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) et peut être déployé dans de nouvelles installations de téléphonie. Il prend en charge les appels entrants du déploiement voix entreprise et du réseau d’opérateur local. Les agents peuvent utiliser Skype entreprise, Lync 2013, Lync 2010, Lync 2010 attendant ou Lync Phone Edition pour prendre les appels routés vers eux.

## <a name="deployment-and-requirements"></a>Déploiement et exigences

L’application Response Group est activée automatiquement lorsque vous déployez Enterprise Voice.

### <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

L’application de Response Group a les mêmes exigences matérielles, exigences relatives au système d’exploitation et logiciels requis en tant que serveurs frontaux.

Si vous utilisez des fichiers Windows Media audio (. WMA) pour la musique et les annonces du groupe réponse, tous les serveurs frontaux ou les éditions standard qui exécutent l’application Response Group doivent avoir installé le runtime du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le runtime Windows Media Format Runtime est installé dans le cadre de l’expérience de bureau Windows.

Response Group utilise des **modules linguistiques** pour la prise en charge de la reconnaissance vocale et de synthèse vocale. Ces technologies vocales servent lors de la configuration de messages (message de bienvenue et autres messages, ou les questions et réponses du système de réponse vocale interactive, par exemple). Par défaut, les 26 modules linguistiques pris en charge sont installés lors du déploiement de Skype entreprise Server.

### <a name="port-requirements"></a>Configuration requise pour les ports

L’application Response Group utilise les ports suivants:

- **Port 5071** pour les demandes d’écoute SIP

- **Port 8404** pour les communications entre les serveurs

    > [!NOTE]
    > Ce port est utilisé pour le service de mise en correspondance et est requis lors du déploiement de l’application Response Group dans un pool qui comporte plusieurs serveurs front-end.

   > [!NOTE]
   > Ces ports sont les paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**. Pour plus d’informations sur cette applet de connexion, consultez la documentation de Skype entreprise Server Management Shell.

### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application Response Group prend en charge le format de fichier Wave (. wav) et le format de fichier Windows Media audio (. WMA) pour les messages de groupe de réponse, la musique en attente ou les questions de réponse vocale interactive.

Le format de fichier audio Windows Media nécessite que le runtime du format Windows Media soit installé sur les serveurs frontaux exécutant Windows Server 2008 R2 et Windows Server 2008. Pour plus d’informations, reportez-vous à « Configuration logicielle requise » plus haut dans cette section.

#### <a name="supported-wave-file-formats"></a>Formats de fichiers Wave pris en charge

Tous les fichiers Wave doivent répondre aux conditions suivantes :

- fichier 8 bits ou 16 bits ;

- format LPCM (Linear Pulse Code Modulation), A-Law ou mu-Law ;

- mono ou stéréo ;

- 4 Mo ou moins.

Pour des performances de fichiers Wave optimales, nous vous recommandons d’utiliser un fichier Wave correspondant au profil suivant : 16 kHz, Mono, 16 bits.

#### <a name="supported-windows-media-audio-file-formats"></a>Formats de fichiers audio Windows Media pris en charge

Si vous utilisez un fichier audio Windows Media, prévoyez d’utiliser de faibles vitesses de transmission et vérifiez les performances de votre système quand il est surchargé.

Vous pouvez utiliser Microsoft Expression Encoder 4 pour convertir un fichier au format audio Windows Media. Pour télécharger Expression Encoder 4 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843), voir.

### <a name="response-group-configuration-tool-requirements"></a>Conditions requises pour l’outil de configuration Response Group

L’outil de configuration de Response Group prend en charge les combinaisons de systèmes d’exploitation et de navigateurs Web décrits dans le tableau ci-dessous.

> [!NOTE]
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.

**Systèmes d’exploitation et navigateurs web pris en charge**

|**Système d’exploitation**|**Navigateur web**|
|:-----|:-----|
|Windows Vista avec Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows 7  <br/> Windows 7 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 avec Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Console des agents Response Group

La console des agents prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.

> [!NOTE]
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.

**Systèmes d’exploitation et navigateurs web pris en charge**

|**Système d’exploitation**|**Navigateur web**|
|:-----|:-----|
|Windows Vista avec Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows 7  <br/> Windows 7 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 avec Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Prise en charge des clients

L’application Response Group prend en charge les clients suivants:

- Client de bureau Skype entreprise

- Client de bureau Lync 2013

- Client de bureau Lync 2010

- Lync 2010 attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> L’application Response Group n’est pas prise en charge sur les clients mobiles Lync.

Le client spécifique que vous pouvez utiliser dépend du type d’utilisateur de groupe de réponse que vous utilisez:

- Les **appelants** peuvent appeler un groupe de réponse à l’aide de l’un des clients répertoriés précédemment, et en utilisant un téléphone standard sur le réseau téléphonique commuté (RTC).

- **Agents** informels (les agents qui ne se connectent pas à leurs groupes pour accepter les appels) peuvent accepter des appels à l’aide de l’assistance standard, de Lync ou de Lync Phone Edition. Les agents informels sont automatiquement connectés à leur groupe lorsque les utilisateurs se connectent à Skype entreprise Server en utilisant l’un de ces clients.

- **Agents officiels** (les agents qui doivent se connecter et se déconnecter de leurs groupes pour accepter les appels) peuvent accepter les appels en utilisant Skype entreprise et en accédant à la console de l’agent à partir de l’élément de menu, ou en utilisant le standard et en accédant à la console de l’agent directement à partir d’Internet Explorer.

## <a name="capacity-planning"></a>Planification de capacité

Le tableau suivant décrit le modèle utilisateur de Response Group que vous pouvez utiliser comme base pour les exigences de planification de capacité.

> [!NOTE]
> Les chiffres du tableau suivant supposent que vous utilisez des fichiers 16 kHz, mono, 16 bits (.wav) pour tous les fichiers audio Response Group. Si vous utilisez d’autres formats de fichier, tels que Windows Media Audio (.wma), les chiffres peuvent changer.

> [!IMPORTANT]
> N’oubliez pas que pour la planification de capacité de récupération d’urgence, chaque pool d’un pool associé doit être capable de gérer les charges de travail de tous les groupes de réponse des deux pools.

**Modèle utilisateur de Response Group**

|**Mesure**|**Par pool <br/> d’éditions d’entreprise (avec 8 serveurs frontaux)**|**Par serveur Standard Edition**|
|:-----|:-----|:-----|
|Appels entrants par seconde  <br/> |Seiz  <br/> |2  <br/> |
|Appels simultanés connectés à la réponse vocale interactive ou à l’attente musicale  <br/> |480  <br/> |60  <br/> |
|Sessions anonymes simultanées (sans messagerie instantanée)  <br/> |224  <br/> |12,70  <br/> |
|Sessions anonymes simultanées (avec messagerie instantanée)  <br/> |64  <br/> |version8  <br/> |
|Agents actifs (formels et informels)  <br/> |2400  <br/> |2400  <br/> |
|Nombre de groupes de recherche  <br/> |800  <br/> |800  <br/> |
|Nombre de groupes de réponse vocale interactive (utilisation de la reconnaissance vocale)  <br/> |400  <br/> |400  <br/> |


