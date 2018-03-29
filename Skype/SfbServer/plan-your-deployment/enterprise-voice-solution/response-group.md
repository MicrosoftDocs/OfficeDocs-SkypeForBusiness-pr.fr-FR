---
title: Planification de l’application Response Group dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planification des groupes de réponse dans Skype pour Business Server Voix Entreprise, qui vous permet de configurer le routage des appels à des groupes d’utilisateurs. Cela inclut les conditions requises pour les fichiers audio.
ms.openlocfilehash: 67b86d6dd15d6dece05261f216c114b377ea3f07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server-2015"></a>Planification de l’application Response Group dans Skype Entreprise Server 2015
 
Planification des groupes de réponse dans Skype pour Business Server Voix Entreprise, qui vous permet de configurer le routage des appels à des groupes d’utilisateurs. Cela inclut les conditions requises pour les fichiers audio.
  
Si votre organisation possède des groupes de personnes qui répondent et gérer certains types d’appels, tels que pour le service client, une assistance interne ou prise en charge de téléphone principal pour un service, vous pouvez déployer l’application Response Group pour gérer ces types d’appels. Le groupe réponse application achemine et les appels entrants vers des files d’attente désigné des personnes, qui sont des agents. L’utilisation des groupes Response Group vous permet d’améliorer l’utilisation des services de support téléphonique et de réduire la charge liée à l’exécution de ces services.
  
Quand un appelant appelle un Response Group, l’appel est acheminé vers un agent en fonction du groupe de recherche ou des réponses de l’appelant aux questions du système de réponse vocale interactive. L’application Response Group utilise des méthodes de routage de groupe réponse standard pour acheminer l’appel vers l’agent disponible suivant. Parmi les méthodes de routage d’appel prises en charge figurent le routage de série, parallèle, le plus longuement inactif, tourniquet (round robin) et le nouveau routage Attendant (dans lequel tous les agents sont appelés en même temps pour tous les appels entrants, quelle que soit leur présence actuelle). 
  
Si aucun agent n’est disponible, l’appel est mis en file d’attente jusqu’à ce qu’un agent se libère. Quand il est en file d’attente, l’appelant entend de la musique jusqu’à ce qu’un agent accepte l’appel. Si la file d’attente est pleine, ou si l’appel arrive à expiration dans la file d’attente, l’appelant entendra probablement un message, puis sera déconnecté ou transféré vers une autre destination. Quand un agent accepte l’appel, l’appelant peut dans certains cas voir l’identité de l’agent, selon la façon dont l’administrateur configure le groupe de réponses. Les agents peuvent être formels, c’est-à-dire qu’ils doivent se connecter au groupe avant de pouvoir accepter les appels y étant acheminés, ou informels, c’est-à-dire qu’ils n’ont pas besoin de se connecter ou déconnecter du groupe pour accepter les appels.
  
> [!NOTE]
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé du site en ligne, appels de groupe réponse ne seront pas routées à cet agent. 
  
> [!NOTE]
> L’application Response Group utilise un service interne, appelé correspondance fabrication, file d’attente des appels et la recherche des agents disponibles. Chaque ordinateur qui exécute l’application Response Group s’exécute le service fabrication de correspondance, mais seulement un service fabrication de correspondance par pool est actif à la fois, les autres sont passifs. En cas d’indisponibilité du service d’établissement des correspondances actif au cours d’une interruption de service imprévue, l’un des services passifs devient actif. L’application de groupe de réponse fait de son mieux pour s’assurer que le routage des appels et queuing se poursuit sans interruption. Cependant, lorsqu’une transition du service d’établissement des correspondances se produit, tous les appels en transfert à ce moment-là sont perdus. Par exemple, si la transition est dû le serveur frontal en panne, tous les appels actuellement gérés par le service de fabrication de la correspondance actif sur ce serveur frontal sont également perdues. 
  
## <a name="response-group-workflows"></a>Flux de travail Response Group

Un flux de travail définit le comportement d’un appel, du déclenchement de la sonnerie du téléphone jusqu’au moment où une personne répond à l’appel. Le flux de travail spécifie la file d’attente à utiliser pour la mise en attente de l’appel et indique la méthode de routage à appliquer aux groupes de recherche ou les questions et les réponses à utiliser pour les groupes Response Group interactifs. Un flux de travail définit également des paramètres, comme un message d’accueil, l’attente musicale, les heures de bureau et les congés.
  
> [!NOTE]
> Vous devez créer des groupes d’agents et des files d’attente avant de créer un flux de travail qui les utilise. 
  
## <a name="management-of-response-groups"></a>Gestion des groupes Response Group

Dans Skype pour Business Server, deux rôles d’administration sont disponibles pour la gestion des groupes de réponse : réponse groupe Gestionnaire et administrateur de groupe de la réponse. Les administrateurs de groupe de réponse peuvent gérer tous les aspects de n’importe quel groupe de réponse. Gestionnaires de groupe de réponse peuvent gérer uniquement certains aspects, et uniquement pour des groupes de la réponse qui leur appartiennent. Le rôle de gestionnaire peut vous aider à réduire vos coûts d’administration, car vous pouvez déléguer la responsabilité limitée pour les groupes de réponse spécifique à tout utilisateur qui est activé pour la Voix Entreprise. Notez qu’un utilisateur peut être à la fois un gestionnaire de groupes de réponse et un administrateur de groupe de la réponse. 
  
Pour prendre en charge le rôle de gestionnaire, application de groupe de la réponse utilise un **Type de Workflow** de gérés ou non gérés. Le tableau ci-dessous décrit les groupes Response Group gérés et non gérés.
  
**Groupes de réponse gérés et non gérés**

|**Type de groupe de réponse**|**Description**|
|:-----|:-----|
|Non géré  <br/> | Aucun gestionnaire n’est affecté aux groupes Response Group non gérés. Seul l’administrateur de groupe de réponse peut configurer ces groupes de réponse. <br/>  Plusieurs groupes Response Group non gérés peuvent partager une file d’attente ou un groupe d’agents. <br/>  Lorsque vous migrez des groupes de réponse à partir d’une version antérieure à Skype pour Business Server, le type est défini sur non. <br/> |
|Géré  <br/> | Les administrateurs de groupe réponse peuvent configurer tous les aspects des groupes de réponse managé. <br/>  Gestionnaires de groupe de réponse ne peut pas afficher ou modifier des groupes de réponse ne sont pas explicitement assignés à ces. <br/>  Les gestionnaires de groupe réponse peuvent configurer uniquement certains paramètres pour les groupes de réponse sont affectées explicitement. <br/>  Les groupes Response Group gérés ne peuvent pas partager des files d’attente ou des groupes d’agents avec d’autres groupes Response Group, qu’ils soient gérés ou non gérés. <br/> |
   
Le tableau suivant décrit les actions que les gestionnaires de groupe réponse peut ou ne peut effectuer pour les groupes de réponse qui leur sont affectées.
  
**Fonctions de gestionnaire de groupe de réponse**

|**Pouvez configurer :**|**Peut créer, supprimer ou configurer :**|**Ne peuvent pas :**|
|:-----|:-----|:-----|
| Agents <br/>  Message d’accueil <br/>  Nom du groupe de réponse <br/>  Description <br/>  Numéro affiché <br/>  Heures d’ouverture <br/>  Attente musicale <br/>  Statut (actif/inactif) <br/>  Flux de travail de groupe de recherche ou flux de travail de réponse vocale interactive (IVR) <br/> | Groupes d’agents <br/>  Files d’attente <br/>  Périodes de congé <br/> | Créer ou supprimer un type de flux de travail <br/>  Modifier les paramètres principaux des groupes Response Group, tels que : **URI SIP**, **Numéro de téléphone** ou **Type de flux de travail**  <br/> |
   
Responsables de groupe réponse peuvent utiliser les outils suivants pour gérer les groupes de réponse désigné. 
  
- Panneau de configuration Skype Entreprise Server
    
    > [!NOTE]
    > Gestionnaires de groupe de réponse peuvent uniquement gérer les paramètres de groupe de réponse grâce à cet outil. Autre Skype pour les paramètres de serveur de l’entreprise ne sont pas disponibles pour les responsables. 
  
- outil de configuration Response Group
    
- Skype Entreprise Server Management Shell
    
Les échelles de groupe réponse bien aux départements ou les environnements de groupe de travail (pour plus d’informations, reportez-vous à la section [Planification de la capacité pour Response Group](http://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) et peut être déployé dans des installations de téléphonie entièrement nouveau. Il prend en charge les appels entrants à partir du réseau local de support et le déploiement de Voix Entreprise. Agents peuvent utiliser Skype pour entreprise, Lync 2013, Lync 2010, la surveillance du Lync 2010 ou Lync Phone Edition pour prendre les appels qui leur est transmis.
  
## <a name="deployment-and-requirements"></a>Déploiement et configuration requise

L’application de groupe de réponse est automatiquement activée lors du déploiement de Voix Entreprise.
  
### <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

L’application de groupe de la réponse a la même configuration matérielle requise, la configuration requise du système d’exploitation et la configuration logicielle requise comme serveurs frontaux. 
  
Si vous utilisez des fichiers Audio Windows Media (.wma) pour les annonces et musique de groupe réponse, tous les serveurs frontaux ou les éditions Standard de serveurs qui exécutent l’application Response Group doivent être installé pour les serveurs exécutant Windows Windows Media Format Runtime Server 2008 R2, ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 R2 ou Windows Server 2012. Pour Windows Server 2008 R2, Windows Media Format Runtime est installé dans le cadre de l’expérience utilisateur Windows.
  
Groupe de réponse utilise la **prise en charge linguistique** pour prendre en charge la reconnaissance vocale et de synthèse vocale. Ces technologies vocales servent lors de la configuration de messages (message de bienvenue et autres messages, ou les questions et réponses du système de réponse vocale interactive, par exemple). Par défaut, le 26 prise en charge des language packs sont installés lorsque vous déployez Skype pour Business Server.
  
### <a name="port-requirements"></a>Configuration requise pour les ports

L’application Response Group utilise les ports suivants :
  
- **5071 de port** pour les requêtes d’écoute SIP
    
- **8404 de port** pour les communications
    
    > [!NOTE]
    > Ce port est utilisé pour le service fabrication de correspondance et est nécessaire lors de l’application de groupe de réponse est déployée dans un groupe qui dispose de plus d’un serveur frontal. 
  
   > [!NOTE]
   > Ces ports sont les paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer** . Pour plus d’informations sur cette applet de commande, consultez le Skype pour obtenir une documentation Business Server Management Shell.
  
### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

Le format de fichier wave (.wav) de groupe de réponse application prend en charge et d’un fichier audio (.wma) de Windows Media format des messages de groupe de réponse, musique d’attente ou aux questions de vocale interactive (IVR) de réponse.
  
Le format de fichier audio Windows Media nécessite que Windows Media Format Runtime est installé sur les serveurs frontaux exécutant Windows Server 2008 R2 et Windows Server 2008. Pour plus d’informations, reportez-vous à « Configuration logicielle requise » plus haut dans cette section.
  
#### <a name="supported-wave-file-formats"></a>Formats de fichiers Wave pris en charge

Tous les fichiers Wave doivent répondre aux conditions suivantes :
  
- fichier 8 bits ou 16 bits ;
    
- format LPCM (Linear Pulse Code Modulation), A-Law ou mu-Law ;
    
- mono ou stéréo ;
    
- 4 Mo ou moins.
    
Pour des performances de fichiers Wave optimales, nous vous recommandons d’utiliser un fichier Wave correspondant au profil suivant : 16 kHz, Mono, 16 bits. 
  
#### <a name="supported-windows-media-audio-file-formats"></a>Formats de fichiers audio Windows Media pris en charge

Si vous utilisez un fichier audio Windows Media, prévoyez d’utiliser de faibles vitesses de transmission et vérifiez les performances de votre système quand il est surchargé.
  
Vous pouvez utiliser Microsoft Expression Encoder 4 pour convertir un fichier au format audio Windows Media. Pour télécharger Microsoft Expression Encoder 4, voir [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).
  
### <a name="response-group-configuration-tool-requirements"></a>Conditions requises pour l’outil de configuration Response Group

L’outil de Configuration de groupe de réponse prend en charge les combinaisons de systèmes d’exploitation et les navigateurs web décrits dans le tableau suivant.
  
> [!NOTE]
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge. 
  
**Systèmes d’exploitation et les navigateurs Web**

|**Système d'exploitation**|**Navigateur Web**|
|:-----|:-----|
|Windows Vista avec Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows 7  <br/> Windows 7 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 avec Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||
|||
   
### <a name="response-group-agent-console"></a>Console des agents Response Group

La console des agents prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.
  
> [!NOTE]
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge. 
  
**Systèmes d’exploitation et les navigateurs Web**

|**Système d'exploitation**|**Navigateur Web**|
|:-----|:-----|
|Windows Vista avec Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows 7  <br/> Windows 7 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 avec Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 avec Service Pack 1  <br/> |Internet Explorer 8 (mode natif)  <br/> Internet Explorer 9 (mode natif)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |
   
## <a name="client-support"></a>Prise en charge des clients

L’application de groupe de réponse prend en charge les clients suivants :
  
- Skype pour client ordinateur de bureau d’entreprise
    
- Client de bureau Lync 2013
    
- Client de bureau Lync 2010
    
- Intendant Lync 2010
    
- Office Communications Server 2007 R2 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> L’application de groupe de réponse n’est pas pris en charge sur les clients mobiles de Lync. 
  
Le client spécifique que vous pouvez utiliser dépend du type d’utilisateur de groupe de réponse que vous êtes : 
  
- Les **appelants** peuvent appeler un groupe de réponse à l’aide de l’un des clients répertoriés précédemment, et en utilisant un téléphone standard sur le réseau téléphonique commuté (RTC).
    
- **Agents informelles** (les agents qui ne signent pas dans et en dehors de leurs groupes d’accepter des appels) peuvent accepter des appels à l’aide de la surveillance du, Lync ou Lync Phone Edition. Agents informels sont automatiquement signés dans leurs groupes lorsqu’ils se connectent à Skype pour Business Server à l’aide d’un de ces clients.
    
- **Agents formels** (les agents qui doivent signer dans et en dehors de leurs groupes d’accepter des appels) peuvent accepter des appels à l’aide de Skype pour les entreprises et de l’accès à la console de l’agent à partir de l’élément de menu ou à l’aide de surveillance et de l’accès à la console de l’agent directement à partir de Internet Explorer.
    
## <a name="capacity-planning"></a>Planification de capacité

Le tableau suivant décrit le modèle d’utilisateur de groupe de réponse que vous pouvez utiliser comme base pour la planification de capacité.
  
> [!NOTE]
> Les chiffres du tableau suivant supposent que vous utilisez des fichiers 16 kHz, mono, 16 bits (.wav) pour tous les fichiers audio Response Group. Si vous utilisez d’autres formats de fichier, tels que Windows Media Audio (.wma), les chiffres peuvent changer. 
  
> [!IMPORTANT]
> N’oubliez pas que pour la planification de capacité de récupération d’urgence, chaque pool d’un pool associé doit être capable de gérer les charges de travail de tous les groupes de réponse des deux pools. 
  
**Modèle de groupe de réponse utilisateur**

|**Métrique**|**Par pool Enterprise Edition <br/> (avec 8 serveurs frontaux)**|**Par serveur Standard Edition server**|
|:-----|:-----|:-----|
|Appels entrants par seconde  <br/> |16  <br/> |2  <br/> |
|Appels simultanés connectés à la réponse vocale interactive ou à l’attente musicale  <br/> |480  <br/> |60  <br/> |
|Sessions anonymes simultanées (sans messagerie instantanée)  <br/> |224  <br/> |28  <br/> |
|Sessions anonymes simultanées (avec messagerie instantanée)  <br/> |64  <br/> |8  <br/> |
|Agents actifs (formels et informels)  <br/> |2400  <br/> |2400  <br/> |
|Nombre de groupes de recherche  <br/> |800  <br/> |800  <br/> |
|Nombre de groupes de réponse vocale interactive (utilisation de la reconnaissance vocale)  <br/> |400  <br/> |400  <br/> |
   

