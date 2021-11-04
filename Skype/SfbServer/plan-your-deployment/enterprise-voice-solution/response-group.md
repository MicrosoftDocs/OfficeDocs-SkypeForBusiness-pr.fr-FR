---
title: Planifier l’application Response Group dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: La planification des groupes Response Groups Skype Entreprise Server Voix Entreprise, qui vous permet de configurer le routage des appels vers des groupes d’utilisateurs. Inclut les conditions requises pour les fichiers audio.
ms.openlocfilehash: 3ca8159ca3d6fc37aa5c8f1f3f88f8188929f71f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767552"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Planifier l’application Response Group dans Skype Entreprise Server

La planification des groupes Response Groups Skype Entreprise Server Voix Entreprise, qui vous permet de configurer le routage des appels vers des groupes d’utilisateurs. Inclut les conditions requises pour les fichiers audio.

Si votre organisation dispose de groupes de personnes qui répondent et gèrent certains types d’appels, tels que le service clientèle, un support technique interne ou le support téléphonique général pour un service, vous pouvez déployer l’application Response Group pour gérer ces types d’appels. L’application Response Group a pour effet d’approvisionnement et de mise en file d’attente des appels entrants vers des personnes désignées, appelées agents. L’utilisation des groupes Response Group vous permet d’améliorer l’utilisation des services de support téléphonique et de réduire la charge liée à l’exécution de ces services.

Lorsqu’un appelant appelle un groupe de réponses, l’appel est acheminé vers un agent basé sur un groupement de postes ou vers les réponses vocales interactives (IVR) aux questions de l’appelant. L’application Response Group utilise des méthodes de routage Response Group standard pour router l’appel vers l’agent disponible suivant. Les méthodes de routage des appels pris en charge incluent le routage série, le plus long inactif, parallèle, round robin et attendant (c’est-à-dire, tous les agents sont appelés en même temps pour chaque appel entrant, quelle que soit leur présence actuelle).

Si aucun agent n’est disponible, l’appel est mis en file d’attente jusqu’à ce qu’un agent se libère. Quand il est en file d’attente, l’appelant entend de la musique jusqu’à ce qu’un agent accepte l’appel. Si la file d’attente est pleine ou si l’appel sort de la file d’attente, l’appelant peut entendre un message, puis est déconnecté ou transféré vers une autre destination, par exemple un autre numéro de téléphone ou une autre messagerie vocale. Quand un agent accepte l’appel, l’appelant peut dans certains cas voir l’identité de l’agent, selon la façon dont l’administrateur configure le groupe de réponses. Les agents peuvent être formels, c’est-à-dire qu’ils doivent se connecter au groupe avant de pouvoir accepter les appels y étant acheminés, ou informels, c’est-à-dire qu’ils n’ont pas besoin de se connecter ou déconnecter du groupe pour accepter les appels.

> [!NOTE]
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de l’local vers le site en ligne, les appels Response Group ne seront pas acheminés vers cet agent.

> [!NOTE]
> L’application Response Group utilise un service interne, appelé Correspondances, pour mettre les appels en file d’attente et rechercher les agents disponibles. Chaque ordinateur qui exécute l’application Response Group exécute le service d’égalisation des correspondances, mais un seul service d’application de correspondance par pool est actif à la fois, les autres sont passifs. En cas d’indisponibilité du service d’établissement des correspondances actif au cours d’une interruption de service imprévue, l’un des services passifs devient actif. L’application Response Group fait de son mieux pour s’assurer que le routage et la mise en file d’accès des appels se poursuivent sans interruption. Cependant, lorsqu’une transition du service d’établissement des correspondances se produit, tous les appels en transfert à ce moment-là sont perdus. Par exemple, si la transition est due à la panne du serveur frontal, tous les appels actuellement gérés par le service de correspondance actif sur ce serveur frontal sont également perdus.

## <a name="response-group-workflows"></a>Flux de travail Response Group

Un flux de travail définit le comportement d’un appel, depuis le déclenchement de la sonnerie du téléphone jusqu’au moment où une personne répond à l’appel. Le flux de travail spécifie la file d’attente à utiliser pour la mise en attente de l’appel et indique la méthode de routage à appliquer aux groupes de recherche, ou les questions et les réponses à utiliser pour les groupes Response Group interactifs. Un flux de travail définit également des paramètres comme un message de bienvenue, l’attente musicale, les heures de bureau et les vacances.

> [!NOTE]
> Vous devez créer des groupes d’agents et des files d’attente avant de créer un flux de travail qui les utilise.

## <a name="management-of-response-groups"></a>Gestion des groupes Response Groups

Dans Skype Entreprise Server, deux rôles de gestion sont disponibles pour la gestion des groupes Response Group : Gestionnaire Response Group et Administrateur Response Group. Les administrateurs Response Group peuvent gérer n’importe quel aspect de n’importe quel groupe Response Group. Les responsables Response Group peuvent gérer uniquement certains aspects, et uniquement pour les groupes Response Group qu’ils possèdent. Le rôle gestionnaire peut vous aider à réduire vos coûts d’administration, car vous pouvez déléguer des responsabilités limitées pour des groupes Response Groups spécifiques à tout utilisateur activé pour Voix Entreprise. Notez qu’un utilisateur peut être à la fois gestionnaire Response Group et administrateur Response Group.

Pour prendre en charge le rôle de gestionnaire, l’application Response Group utilise un **type** de flux de travail géré ou non géré. Le tableau suivant décrit les groupes Response Group gérés et non gérés.

**Groupes Response Group gérés et non gérés**

|**Type de groupe Response Group**|**Description**|
|:-----|:-----|
|Non gestion  <br/> | Aucun gestionnaire n’est affecté aux groupes Response Group non gérés. Seul l’administrateur Response Group peut configurer ces groupes Response Group. <br/>  Plusieurs groupes Response Group non gérés peuvent partager une file d’attente ou un groupe d’agents. <br/>  Lorsque vous migrez des groupes Response Groups d’une version antérieure vers Skype Entreprise Server, le type est définie sur Non gestion. <br/> |
|Géré  <br/> | Les administrateurs Response Group peuvent configurer n’importe quel aspect des groupes Response Group gérés. <br/>  Les responsables Response Group ne peuvent pas afficher ou modifier les groupes Response Group qui ne leur sont pas explicitement affectés. <br/>  Les responsables Response Group ne peuvent configurer que certains paramètres pour les groupes Response Group qui leur sont explicitement attribués. <br/>  Les groupes Response Group gérés ne peuvent pas partager des files d’attente ou des groupes d’agents avec d’autres groupes Response Group, qu’ils soient gérés ou non gérés. <br/> |

Le tableau suivant décrit les actions que les responsables Response Group peuvent et ne peuvent pas effectuer pour les groupes Response Group qui leur sont affectés.

**Fonctions du gestionnaire Response Group**

|**Peut configurer :**|**Peut créer, supprimer ou configurer :**|**Impossible :**|
|:-----|:-----|:-----|
| Agents <br/>  Message d’accueil <br/>  Nom de Response Group <br/>  Description <br/>  Numéro affiché <br/>  Heures d’ouverture <br/>  Attente musicale <br/>  Statut (actif/inactif) <br/>  Flux de travail de groupe de recherche ou flux de travail de réponse vocale interactive (IVR) <br/> | Groupes d’agents <br/>  Files d’attente <br/>  Périodes de congé <br/> | Créer ou supprimer un type de flux de travail <br/>  Modifier les paramètres principaux des groupes Response Group, tels que : **URI SIP**, **Numéro de téléphone** ou **Type de flux de travail**  <br/> |

Les responsables Response Group peuvent utiliser les outils suivants pour gérer leurs groupes Response Group désignés.

- Panneau de configuration Skype Entreprise Server

    > [!NOTE]
    > Les responsables Response Group peuvent uniquement gérer les paramètres Response Group à l’aide de cet outil. Les autres Skype Entreprise Server de gestion ne sont pas disponibles pour les responsables.

- outil de configuration Response Group

- Skype Entreprise Server Management Shell

Response Group s’dimensionnait bien aux environnements de service ou de groupe de travail (pour plus d’informations, voir Planification de la capacité pour [Response Group)](/previous-versions/office/lync-server-2013/lync-server-2013-capacity-planning-for-response-group)et peut être déployé dans de nouvelles installations téléphoniques. Il prend en charge les appels entrants provenant Voix Entreprise déploiement et du réseau de l’opérateur local. Les agents peuvent utiliser Skype Entreprise, Lync 2013, Lync 2010, Lync 2010 Attendant ou Lync Téléphone Edition pour prendre les appels qui leur sont acheminés.

## <a name="deployment-and-requirements"></a>Déploiement et conditions requises

L’application Response Group est automatiquement activée lorsque vous déployez Voix Entreprise.

### <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

L’application Response Group a la même configuration matérielle requise, la même configuration requise pour le système d’exploitation et les mêmes logiciels que les serveurs frontaux.

Si vous utilisez des fichiers Windows Media Audio (.wma) pour la musique et les annonces Response Group, le runtime du format multimédia Windows doit être installé sur tous les serveurs frontaux ou Standard Editions server qui exécutent l’application Response Group pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le Windows du format multimédia est installé dans le cadre de Windows Expérience utilisateur.

Response Group utilise **des packs de langue** pour prendre en charge la reconnaissance vocale et la reconnaissance vocale. Ces technologies vocales servent lors de la configuration de messages (message de bienvenue et autres messages, ou les questions et réponses d’une réponse vocale interactive, par exemple). Par défaut, les 26 packs de langue pris en charge sont installés lorsque vous déployez Skype Entreprise Server.

### <a name="port-requirements"></a>Configuration requise pour les ports

L’application Response Group utilise les ports suivants :

- **Port 5071 pour les**   demandes d’écoute SIP

- **Port 8404 pour**   les communications entre serveurs

    > [!NOTE]
    > Ce port est utilisé pour le service d’application de correspondance et est requis lorsque l’application Response Group est déployée dans un pool qui possède plusieurs serveurs frontux.

   > [!NOTE]
   > Ces ports sont des paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**. Pour plus d’informations sur cette cmdlet, voir la documentation Skype Entreprise Server Management Shell.

### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application Response Group prend en charge le format de fichier wave (.wav) et le format de fichier audio Windows Media (.wma) pour les messages Response Group, la musique d’attente ou les questions de réponse vocale interactive (IVR).

Le format de fichier audio Windows Media nécessite que le runtime du format multimédia Windows soit installé sur les serveurs frontaux exécutant Windows Server 2008 R2 et Windows Server 2008. Pour plus d’informations, voir « Configuration logicielle requise » plus haut dans cette section.

#### <a name="supported-wave-file-formats"></a>Formats de fichiers Wave pris en charge

Tous les fichiers son doivent répondre aux conditions suivantes :

- fichier 8 bits ou 16 bits ;

- format LPCM (Linear Pulse Code Modulation), A-Law ou mu-Law ;

- mono ou stéréo ;

- 4 Mo ou moins.

Pour des performances de fichiers son optimales, il est recommandé d’utiliser un fichier son correspondant au profil suivant : 16 kHz, Mono, 16 bits.

#### <a name="supported-windows-media-audio-file-formats"></a>Formats de fichiers audio Windows Media pris en charge

Si vous utilisez un fichier audio Windows Media, prévoyez d’utiliser de faibles vitesses de transmission et vérifiez les performances de votre système quand il est surchargé.

Vous pouvez utiliser Microsoft Expression Encoder 4 pour convertir un fichier au format audio Windows Media. Pour télécharger Expression Encoder 4, voir [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) .

### <a name="response-group-configuration-tool-requirements"></a>Configuration requise pour l'outil de configuration pour Response Group

L’outil de configuration Response Group prend en charge les combinaisons de systèmes d’exploitation et de navigateurs web décrites dans le tableau suivant.

> [!NOTE]
> Les versions 32 bits ou 64 bits des systèmes d'exploitation sont prises en charge. Seules les versions 32 bits d'Internet Explorer sont prises en charge.

**Systèmes d’exploitation et navigateurs web pris en charge**

|**Système d’exploitation**|**Navigateur Web**|
|:-----|:-----|
|Windows Vista avec Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows 7  <br/> Windows 7 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 avec Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Console des agents Response Group

La console des agents prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.

> [!NOTE]
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.

**Systèmes d’exploitation et navigateurs web pris en charge**

|**Système d’exploitation**|**Navigateur Web**|
|:-----|:-----|
|Windows Vista avec Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows 7  <br/> Windows 7 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 avec Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Prise en charge des clients

L’application Response Group prend en charge les clients suivants :

- Skype Entreprise client de bureau

- Client de bureau Lync 2013

- Client de bureau Lync 2010

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> L’application Response Group n’est pas prise en charge sur les clients mobiles Lync.

Le client spécifique que vous pouvez utiliser dépend du type d’utilisateur Response Group que vous êtes :

- Les **appelants** peuvent appeler un groupe de réponse à l’aide de l’un des clients répertoriés précédemment, et en utilisant un téléphone standard sur le réseau téléphonique commuté (RTC).

- **Les agents** informels (agents qui ne se connectent pas à leurs groupes et ne se dé connectent pas à leurs groupes pour accepter des appels) peuvent accepter des appels à l’aide de Attendant, Lync ou Lync Téléphone Edition. Les agents informels sont automatiquement connectés à leurs groupes lorsqu’ils se connectent Skype Entreprise Server à l’aide de l’un de ces clients.

- Les **agents** formels (agents qui doivent se connecter et se sortir de leurs groupes pour accepter des appels) peuvent accepter des appels à l’aide de Skype Entreprise et accéder à la console de l’agent à partir de l’élément de menu, ou à l’aide de Attendant et d’accéder à la console de l’agent directement à partir d’Internet Explorer.

## <a name="capacity-planning"></a>Planification de la capacité

Le tableau suivant décrit le modèle utilisateur Response Group que vous pouvez utiliser comme base pour les besoins de planification de la capacité.

> [!NOTE]
> Les chiffres du tableau suivant supposent que vous utilisez des fichiers 16 kHz, mono, 16 bits (.wav) pour tous les fichiers audio Response Group. Si vous utilisez d’autres formats de fichier, tels que Windows Media Audio (.wma), les chiffres peuvent changer.

> [!IMPORTANT]
> N’oubliez pas que pour la planification de capacité de récupération d’urgence, chaque pool d’un pool associé doit être capable de gérer les charges de travail de tous les groupes de réponse des deux pools.

**Modèle utilisateur de Response Group**

|**Métrique**|**Par Êdition Entreprise pool <br/> (avec 8 serveurs frontux)**|**Par serveur Standard Edition**|
|:-----|:-----|:-----|
|Appels entrants par seconde  <br/> |16  <br/> |2  <br/> |
|Appels simultanés connectés à la réponse vocale interactive ou à l’attente musicale  <br/> |480  <br/> |60  <br/> |
|Sessions anonymes simultanées (sans messagerie instantanée)  <br/> |224  <br/> |28  <br/> |
|Sessions anonymes simultanées (avec messagerie instantanée)  <br/> |64  <br/> |8   <br/> |
|Agents actifs (formels et informels)  <br/> |2400  <br/> |2400  <br/> |
|Nombre de groupes de recherche  <br/> |800  <br/> |800  <br/> |
|Nombre de groupes de réponse vocale interactive (utilisation de la reconnaissance vocale)  <br/> |400  <br/> |400  <br/> |