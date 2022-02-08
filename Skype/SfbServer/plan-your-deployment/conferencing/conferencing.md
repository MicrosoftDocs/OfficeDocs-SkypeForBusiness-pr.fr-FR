---
title: Planifier les conférences dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les fonctionnalités de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 669c87bd2c5eae3944a586e289bbeac3fd4409df
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394986"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planifier les conférences dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les fonctionnalités de conférence dans Skype Entreprise Server.
  
La conférence dans Skype Entreprise Server permet aux utilisateurs de se réunir et d’organiser des conférences en ligne à l’aide de leur client Skype Entreprise au lieu que tout le monde se rassemble dans la même salle. Les participants à la réunion peuvent se connecter à une réunion avec leur client Skype Entreprise pour une expérience audio et vidéo complète, ou se connecter à une conférence à l’aide d’un téléphone. Les conférences offrent également une prise en charge de la messagerie instantanée, du partage de bureau et d’application, ainsi que des tableaux blancs interactifs.
  
Cette rubrique comprend les sections suivantes :
  
- Fonctionnalités et fonctionnalités de conférence
    
- Composants de conférence
    
- Stratégies de conférence
    
- Prise en charge des grandes réunions
    
- Déterminer les besoins de votre organisation
    
## <a name="conferencing-features-and-capabilities"></a>Fonctionnalités et fonctionnalités de conférence

Quatre types de conférences sont disponibles dans Skype Entreprise Server : conférence web, conférence audio et vidéo (A/V), conférences de conférences d’appels et conférences par messagerie instantanée. 
  
Vous pouvez choisir d’activer tous les types de conférence ou d’utiliser un seul type, en fonction de vos besoins. Par exemple, vous pouvez activer tous les types, y compris les conférences rendez-vous, pour permettre aux utilisateurs qui ne peuvent pas participer à une conférence avec un client Skype Entreprise d’appeler et de participer à la réunion audio à partir d’un téléphone. Lorsque vous déployez Skype Entreprise Server, les fonctionnalités de conférence par messagerie instantanée sont déployées automatiquement ; vous spécifiez s’il faut déployer les conférences web, audio/vidéo et les conférences téléphoniques à l’aide du Générateur de topologie. Pour plus d’informations, [voir Deploy conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
Les sous-sections suivantes décrivent les fonctionnalités de chaque type de conférence.
  
### <a name="web-conferencing"></a>Conférence web

La conférence web permet aux participants à la réunion de collaborer sur des documents partagés au cours de la réunion, et au présentateur de la réunion de partager des applications via le client Skype Entreprise réunion. La conférence web offre les fonctionnalités suivantes : 
  
- **Tableau blanc et annotations.** Un tableau blanc est une surface vierge que vous pouvez utiliser à des fins de collaboration, avec du texte, de l’encre, des dessins et des images. Tous les participants à une réunion peuvent voir les annotations qui y sont ajoutées. La fonctionnalité de tableau blanc favorise la collaboration en permettant aux participants à une réunion d’échanger des idées, de débattre, de prendre des notes, etc.
    
- **Interrogation.** La fonctionnalité d’interrogation améliore la collaboration en permettant aux présentateurs de déterminer rapidement les préférences des participants. Au cours des réunions et des conversations en ligne, les présentateurs peuvent avoir recours à l’interrogation pour recueillir des réponses anonymes des participants. Tous les présentateurs peuvent voir les résultats et choisir soit de les montrer à tous les participants, soit de les masquer.
    
- **Partage d’application et partage de bureau.** Au cours d’une conférence, le présentateur de la réunion peut partager l’intégralité de son bureau, une application individuelle ou des moniteurs individuels dans un environnement multi-moniteur. Outre l’affichage du contenu, les autres participants à la conférence peuvent demander le contrôle de l’écran du présentateur et, avec autorisation, interagir avec le contenu (y compris le défilement et la modification). Les participants à la réunion peuvent également prendre le relais en tant que présentateur et commencer à partager du contenu pendant la réunion.
    
- **PowerPoint partage.** Permet aux utilisateurs de partager PowerPoint présentations dans la réunion via un serveur Office Web Apps, ce qui permet :
    
  - Affichages haute résolution et prise en charge des fonctionnalités PowerPoint, telles que les animations, les transitions de diapositives et la vidéo incorporée.
    
  - Les appareils mobiles peuvent accéder à ces présentations.
    
  - Les utilisateurs  ayant les autorisations appropriées peuvent faire défiler une présentation PowerPoint indépendamment de la présentation elle-même. Par exemple, pendant que Ken présente son diaporama, Elle peut regarder n’importe quelle diapositive sans affecter la présentation de Ken.
    
### <a name="audio-and-video-conferencing"></a>Audioconférence et vidéo

La conférence audio et vidéo permet l’audio et la vidéo dans la réunion. L’audio permet aux participants de se parler comme s’ils étaient dans la même salle. La vidéo active l’affichage vidéo dans le client Skype Entreprise de tous les participants ou présentateurs qui rejoignent la réunion à l’aide d’une caméra web ou d’un appareil de conférence qui prend en charge la vidéo.
  
 Skype Entreprise Server fournit plusieurs fonctionnalités que les utilisateurs peuvent utiliser pour configurer l’expérience d’audioconférence pour l’utilisateur, notamment :
  
- **Désactiver le son de l’audience.** Le présentateur peut utiliser ce paramètre pour désactiver le micro de tous les participants audio de la conférence et placer celle-ci dans un état où les personnes qui ne sont pas des présentateurs ne peuvent pas réactiver leur micro.
    
- **Annonces d’entrée/sortie de conférence.** Si vous avez activé la conférence rendez-vous, les présentateurs peuvent utiliser ce paramètre pour activer ou désactiver les annonces d’entrée et de sortie afin de limiter les distractions durant une conférence.
    
- **Ajout d’un utilisateur par appel sortant.** Les présentateurs et les participants qui ont reçu des autorisations peuvent ajouter des numéros PSTN aux conférences et faire en sorte que la conférence compose ces numéros.
    
  Skype Entreprise Server propose plusieurs fonctionnalités que les utilisateurs peuvent utiliser pour configurer l’expérience de visioconférence pour l’utilisateur, notamment :
  
- **Vue Galerie.** Dans les visioconférences qui comportent plus de deux personnes, les utilisateurs voient automatiquement tous les participants à la conférence. Si celle-ci comporte plus de cinq participants, la vidéo des participants les plus actifs apparaît sur la ligne supérieure et seule la photo apparaît pour les autres participants. La vidéo à plusieurs est activée par défaut.
    
- **Vidéo panoramique.** Si un périphérique de visioconférence RoundTable est installé dans la salle de conférence, cette fonctionnalité offre une vue à 360 degrés de la salle de conférence. Le clip vidéo panoramique est disponible uniquement avec les périphériques RoundTable.
    
- **Mode vidéo Présentateur uniquement.** Les présentateurs peuvent configurer la réunion de sorte que seule la vidéo du présentateur soit affichée. Ceci empêche toute distraction lors des réunions à grande échelle, lorsque plusieurs flux vidéo sont disponibles et verrouillés à différentes sources. Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable.
    
- **Vidéo à la une.** Les présentateurs peuvent configurer la réunion de sorte que seule la vidéo d’un participant sélectionné qui est une source vidéo soit visible par les autres participants à la conférence. Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable pour la vidéo panoramique.
    
### <a name="dial-in-conferencing"></a>Conférence rendez-vous

La conférence rendez-vous permet aux participants à la réunion de participer à la partie audio d’une réunion en appelant à la réunion à partir d’un téléphone. Une conférence rendez-vous est un sous-ensemble d’une audioconférence et nécessite une configuration supplémentaire. Pour plus d’informations sur la conférence [rendez-vous, voir Plan for dial-in conferencing in Skype Entreprise Server](dial-in-conferencing.md) and [Configure dial-in conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conférence par messagerie instantanée

La conférence de messagerie instantanée permet à plus de deux parties de communiquer au cours d’une seule session de messagerie instantanée. Pour plus d’informations sur la conférence par messagerie instantanée, voir Planifier la messagerie instantanée et [la présence dans Skype Entreprise Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Composants de conférence

Les composants qui la prise en charge des fonctionnalités de conférence sont les suivants :
  
- **Service d’application.** Le service d’application fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées. La conférence téléphonique utilise deux applications UC qui nécessitent le service d’application : Assistant de conférence et Annonce de conférence. Le service d’application est installé et activé par défaut sur chaque serveur frontal d’un pool frontal. Il est également installé sur chaque serveur Édition Standard pour activer et configurer la conférence téléphonique.
    
- **application Assistant de conférence.** Le application Assistant de conférence est une application de communications unifiées qui accepte les appels PSTN (réseau téléphonique commuté), lit des invites et joint les appels à une conférence A/V. Le application Assistant de conférence est installé et activé par défaut lorsque vous activez la conférence téléphonique.
    
- **application Annonce de conférence.** Le application Annonce de conférence est une application de communications unifiées qui lit des tonalités et des invites aux participants PSTN lors de certaines actions, par exemple lorsque les participants rejoignent ou quittent une conférence, que les participants sont mis en sourdine ou non, qu’une personne entre dans la salle d’accueil de la conférence ou que la conférence est verrouillée ou déverrouillée. application Annonce de conférence prend également en charge les commandes DTMF (dual-tone multi-frequency) à partir du clavier du téléphone. Le application Annonce de conférence est automatiquement installé et activé par défaut lorsque vous activez la conférence téléphonique.
    
- **Page de conférences Paramètres conférence.** La page Paramètres de conférence rendez-vous affiche les numéros d’accès aux conférences avec leurs langues disponibles, les informations de conférence affectées (c’est-à-dire, pour les réunions qui ne doivent pas être programmées) et les contrôles DTMF en conférence, et prend en charge la gestion du code confidentiel et des informations de conférence attribuées. La page de conférence Paramètres est installée automatiquement dans le cadre des services Web.
    
- **Serveur de médiation et passerelle PSTN.** La conférence téléphonique nécessite un serveur de médiation pour traduire la signalisation (et les médias dans certaines configurations) entre Skype Entreprise Server et la passerelle PSTN, et une passerelle PSTN pour traduire la signalisation et le média entre le serveur de médiation et la passerelle PSTN. Pour les conférences téléphoniques, vous devez déployer au moins un serveur de médiation et au moins l’un des services suivants :
    
  - Passerelle PSTN
    
  - IP-PBX
    
  - Contrôleur SBC (Session Border Controller) (pour un fournisseur de services de téléphonie Internet auquel vous vous connectez en configurant une connexion SIP)
    
  > [!NOTE]
  > Si vous déployez également Voix Entreprise, le serveur de médiation et les passerelles PSTN font partie du Voix Entreprise déploiement. Si vous déployez pas Voix Entreprise, vous devez déployer au moins un serveur de médiation et une passerelle PSTN, un système IP-PBX ou un contrôleur de frontière de session pour la conférence rendez-vous. 
  
- **Magasin de fichiers.** Le magasin de fichiers est utilisé pour le nom enregistré des fichiers audio. Le magasin de fichiers est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.
    
- **Magasin d’utilisateurs.** Le magasin d’utilisateurs est utilisé pour stocker les Skype Entreprise Server des utilisateurs. Les codes confidentiels sont hachés. Le magasin d’utilisateurs est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.
    
- **Office Web Apps Server.** Pour utiliser les fonctionnalités de conférence web, les administrateurs doivent installer Office Web Apps Server et configurer Skype Entreprise Server pour communiquer avec Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Stratégies de conférence

Pour appliquer les stratégies de votre organisation et contrôler l’utilisation de la bande passante, vous pouvez définir des stratégies pour les types de réunions que les utilisateurs peuvent organiser. Vous pouvez définir un large éventail de stratégies de conférence et les affecter à des utilisateurs individuels et à des groupes d’utilisateurs. Vous pouvez également définir des stratégies régissant les conversations d’égal à égal. Pour plus d’informations sur la définition des stratégies de conférence, voir Gérer les stratégies de conférence [dans Skype Entreprise Server](../../manage/conferencing/conferencing-policies.md). Pour plus d’informations sur la gestion de la bande passante, voir [Plan for call admission control in Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Prise en charge des grandes réunions

La taille des réunions que les Skype Entreprise Server peuvent prendre en charge varie selon que la conférence est hébergée sur un pool partagé ou dédié :
  
- Sur un pool partagé, Skype Entreprise Server pouvez héberger des réunions avec jusqu’à 250 utilisateurs. Un pool partagé est un pool qui héberge toutes les charges de travail Skype Entreprise Server y compris la messagerie instantanée et la présence, les conférences et les Voix Entreprise. 
    
- Sur un pool dédié, Skype Entreprise Server peut prendre en charge des réunions comprenant jusqu’à 1 000 participants à l’aide de conférences web et audio/vidéo (A/V), y compris le partage PowerPoint présentations. Cette prise en charge requiert un pool dédié configuré pour prendre en charge de grandes réunions et géré pour n’héberger qu’une seule grande réunion à la fois. 
    
Pour plus d’informations sur la gestion des grandes réunions, voir Planifier les grandes réunions [dans Skype Entreprise Server](large-meetings.md).
  
Si votre organisation nécessite des fonctionnalités de réunion plus importantes, vous devez envisager d’implémenter un environnement hybride qui tire parti de la diffusion Réunion Skype, un service en ligne qui fait partie de Microsoft 365 et Office 365. Réunion Skype diffusion permet aux utilisateurs d’héberger et de diffuser des réunions à un large public en ligne de 10 000 participants au plus. L’utilisation de Réunion Skype diffusion nécessite que Skype Entreprise Server soit déjà configuré dans une configuration hybride avec une organisation Microsoft 365 ou Office 365 production. Un client en ligne doit être établi en tant que prérequis pour tous les utilisateurs. Si vous souhaitez déployer une solution hybride qui peut tirer parti de Réunion Skype Broadcast, voir Configurer votre déploiement local pour [Réunion Skype Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Déterminer les besoins de votre organisation

Lorsque vous déterminez les fonctionnalités de conférence à déployer, vous devez tenir compte des fonctionnalités que vous souhaitez mettre à disposition de vos utilisateurs et des capacités de votre bande passante réseau. La liste suivante vous guide tout au long du processus de planification de conférence pour déterminer les fonctionnalités de conférence à déployer, en fonction des besoins de votre organisation.
  
> [!NOTE]
> Lorsque vous activez la conférence au déploiement, vous activez automatiquement la conférence web et la conférence A/V. Vous pouvez toutefois désactiver des fonctionnalités spécifiques en configurant des stratégies de conférence comme décrit précédemment dans cette rubrique. 
  
- **Souhaitez-vous activer la conférence web, qui inclut la collaboration sur des documents et le partage d’application ?**
    
    Si c’est le cas, vous devez activer la conférence pour votre pool frontal à l’aide de l’outil de planification ou du Générateur de topologies. Pour plus d’informations, [voir Deploy conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Le partage d’application requiert et utilise plus de bande passante réseau que la collaboration sur des documents. Skype Entreprise Server fournit un mécanisme de limitation pour contrôler chaque session de partage d’application. Par défaut, il est défini à 1,5 Ko/seconde pour chaque session. Si vous ne souhaitez pas activer le partage d’application, mais que vous souhaitez la collaboration sur des documents, vous pouvez activer la conférence et utiliser des stratégies de conférence pour désactiver le partage d’application. Pour plus d’informations sur la configuration des stratégies de conférence, voir Gérer les stratégies de conférence [dans Skype Entreprise Server](../../manage/conferencing/conferencing-policies.md).
    
    Pour permettre aux utilisateurs de partager PowerPoint présentations, vous devez configurer Office Web Apps Server. Pour plus d’informations sur la configuration Office Web Apps Server, voir Configurer l’intégration avec [Office Web Apps Server dans Skype Entreprise Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Voulez-vous activer la conférence audio et vidéo ?**
    
    Si c’est le cas, vous devez activer la conférence pour votre pool frontal à l’aide de l’outil de planification ou du Générateur de topologies. Pour plus d’informations, [voir Deploy conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    La conférence audio et vidéo nécessite et utilise plus de bande passante réseau que la conférence web (qui inclut la collaboration sur des documents et le partage d’applications). Si vous ne souhaitez pas activer la conférence audio et vidéo, mais que vous souhaitez activer la conférence web, vous pouvez activer la conférence et utiliser des stratégies de conférence pour désactiver les conférences A/V.
    
    Si vous souhaitez activer les audioconférences, mais pas les conférences vidéo, vous pouvez activer la conférence A/V et utiliser des stratégies de conférence pour empêcher les visioconférences. De même, vous pouvez activer la conférence A/V, et autoriser uniquement certains utilisateurs à initier une conférence A/V ou à y prendre part. 
    
    Pour plus d’informations sur la configuration des stratégies de conférence, voir Gérer les stratégies de conférence [dans Skype Entreprise Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Voix Entreprise n’est pas nécessaire pour utiliser la conférence A/V. Si vous activez la conférence A/V, vos utilisateurs peuvent ajouter de l’audio à leurs conférences pourvu qu’ils disposent de périphériques audio, et ce même si vous utilisez un autocommutateur privé (PBX) pour votre solution téléphonique. 
  
- **Souhaitez-vous autoriser les utilisateurs à participer à la partie audio des conférences lorsqu’ils utilisent un téléphone PSTN ?**
    
    Dans l’affirmative, déployez et activez la conférence rendez-vous. Les utilisateurs invités, à l’intérieur et à l’extérieur de votre organisation, peuvent alors prendre part à la partie audio des conférences par l’intermédiaire d’un téléphone PSTN.
    
    La conférence rendez-vous est une fonctionnalité facultative que vous pouvez configurer lorsque vous déployez Skype Entreprise Server conférence. Bien que la conférence dial-in utilise certains des mêmes composants que Voix Entreprise, vous pouvez déployer la conférence dial-in même si vous ne déployez pas Voix Entreprise. La conférence téléphonique prend en charge à la fois les utilisateurs d’entreprise et les utilisateurs anonymes. Pour plus d’informations sur la configuration de la conférence rendez-vous pour les utilisateurs d’entreprise et anonymes, voir [Deploy conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md) and [Configure dial-in conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Souhaitez-vous permettre aux utilisateurs externes Skype Entreprise clients de participer à des conférences ?**
    
    En permettant la participation externe aux réunions, vous optimisez votre investissement dans Skype Entreprise Server. Les utilisateurs externes peuvent inclure les catégories suivantes :
    
  - **Utilisateurs distants.** Les utilisateurs de votre organisation, lorsqu’ils travaillent en dehors de vos pare-feu et utilisent leurs ordinateurs portables ou d’Skype Entreprise Server périphériques.
    
  - **Utilisateurs fédérés.** Utilisateurs des entreprises avec qui vous travaillez et qui exécutent également Skype Entreprise Server. Pour autoriser vos utilisateurs à contacter facilement ces utilisateurs, créez des relations fédérées avec ces entreprises.
    
  - **Utilisateurs anonymes.** Tous les autres utilisateurs externes qui sont invités par vos utilisateurs à participer à des conférences spécifiques. Un organisateur de réunion qui appartient à votre entreprise peut envoyer à un utilisateur externe, par courrier électronique, une invitation à participer à une conférence. Le courrier électronique inclut un lien sur lequel l’utilisateur externe peut cliquer pour prendre part à la conférence.
    
    Si vous souhaitez autoriser les utilisateurs externes, vous devez déployer des serveurs Edge. En outre, avec les serveurs Edge déployés, vous pouvez créer des relations fédérées avec d’autres organisations(par exemple, vos clients ou fournisseurs) et les utilisateurs de ces organisations peuvent collaborer plus facilement avec vos utilisateurs.
    
    Pour plus d’informations sur le déploiement des serveurs Edge, voir Plan for Edge Servers and Deploy Edge Servers. Pour plus d’informations sur l’activation de l’accès externe pour Office Web Apps Server, voir [Configure integration with Office Web Apps Server in Skype Entreprise Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Souhaitez-vous contrôler les clients qui peuvent participer Skype Entreprise Server réunions ?**
    
    Dans l’affirmative, vous devez configurer la page de participation aux réunions, afin que seules les options clientes que vous souhaitez prendre en charge soient disponibles. Chaque fois qu’un utilisateur clique sur un lien pour participer à une réunion Skype Entreprise Server, il détecte si un client est déjà installé sur l’ordinateur. Il démarre alors le client par défaut et ouvre la page de participation à la réunion qui contient des liens vers d’autres clients. La page de réunion contient toujours l’option d’utilisation Application Web Skype Entreprise. Outre cette option, vous pouvez décider d’inclure ou non des liens pour Attendee et les versions antérieures de Communicator. 
    

