---
title: Planifier des conférences dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Résumé : consultez cette rubrique pour en savoir plus sur les fonctionnalités et les fonctionnalités de conférence dans Skype entreprise Server.'
ms.openlocfilehash: 1c67eecda6c7691dfbb042f4743733b73864a426
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221164"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planifier des conférences dans Skype entreprise Server
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les fonctionnalités et les fonctionnalités de conférence dans Skype entreprise Server.
  
La fonctionnalité de conférence dans Skype entreprise Server permet aux utilisateurs de répondre à des conférences en ligne à l’aide de leur client Skype entreprise au lieu de tout le monde dans la même pièce. Les participants à la réunion peuvent se connecter à une réunion avec leur client Skype entreprise pour une expérience audio et vidéo complète, ou pour accéder à une conférence à l’aide d’un téléphone. Les conférences prennent également en charge la messagerie instantanée, le partage de bureau et d’applications, ainsi que les tableaux blancs interactifs.
  
Cette rubrique comprend les sections suivantes :
  
- Fonctionnalités et fonctionnalités de conférence
    
- Composants de conférence
    
- Stratégies de conférence
    
- Prise en charge des grandes réunions
    
- Déterminer les besoins de votre organisation
    
## <a name="conferencing-features-and-capabilities"></a>Fonctionnalités et fonctionnalités de conférence

Il existe quatre types de conférence disponibles dans Skype entreprise Server : conférence Web, conférence audio et vidéo (A/V), Conférence rendez-vous et Conférence par messagerie instantanée. 
  
Vous pouvez choisir d’activer tous les types de conférence ou d’utiliser un seul type, selon vos besoins. Par exemple, vous pouvez activer tous les types, y compris la Conférence rendez-vous, pour autoriser les utilisateurs qui ne peuvent pas participer à une conférence avec un client Skype entreprise à appeler et participer à la réunion audio à partir d’un téléphone. Lorsque vous déployez Skype entreprise Server, les fonctionnalités de conférence par messagerie instantanée sont déployées automatiquement ; vous spécifiez s’il faut déployer Web, A/V et la Conférence rendez-vous à l’aide du générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
Les sous-sections suivantes décrivent les fonctionnalités et les fonctionnalités de chaque type de conférence.
  
### <a name="web-conferencing"></a>Conférence web

La conférence Web permet aux participants d’une réunion de collaborer sur des documents partagés au cours de la réunion, et pour le présentateur de la réunion de partager des applications via le client Skype entreprise. La conférence Web offre les fonctionnalités suivantes : 
  
- **Tableau blanc et annotations.** Un tableau blanc est une surface vierge que vous pouvez utiliser à des fins de collaboration, avec du texte, de l’encre, des dessins et des images. Tous les participants à une réunion peuvent voir les annotations qui y sont ajoutées. La fonctionnalité de tableau blanc favorise la collaboration en permettant aux participants à une réunion d’échanger des idées, de débattre, de prendre des notes, etc.
    
- **Interrogation.** La fonctionnalité d’interrogation améliore la collaboration en permettant aux présentateurs de déterminer rapidement les préférences des participants. Au cours des réunions et des conversations en ligne, les présentateurs peuvent avoir recours à l’interrogation pour recueillir des réponses anonymes des participants. Tous les présentateurs peuvent voir les résultats et choisir soit de les montrer à tous les participants, soit de les masquer.
    
- **Partage d’application et partage de bureau.** Au cours d’une conférence, le présentateur de réunion peut partager l’ensemble de son bureau, une application individuelle ou des moniteurs individuels dans un environnement à plusieurs moniteurs. Outre le fait de simplement afficher le contenu, les autres participants à la Conférence peuvent demander le contrôle de l’écran du présentateur et, avec l’autorisation, interagir avec le contenu (y compris le défilement et la modification). Les participants à la réunion peuvent également prendre le rôle de présentateur et démarrer le partage de contenu pendant la réunion.
    
- **Partage PowerPoint.** Permet aux utilisateurs de partager des présentations PowerPoint dans la réunion par le biais d’un serveur Office Web Apps Server, ce qui permet :
    
  - Affichage haute résolution et prise en charge des fonctionnalités PowerPoint, telles que les animations, les transitions de diapositives et la vidéo incorporée.
    
  - Les appareils mobiles peuvent accéder à ces présentations.
    
  - Les utilisateurs disposant des autorisations appropriées peuvent faire défiler une présentation PowerPoint indépendamment de la présentation proprement dite. Par exemple, quand Ken présente son diaporama, Heidi peut examiner les diapositives auxquelles il souhaite sans affecter la présentation de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conférence audio et vidéo

La conférence audio et vidéo permet l’audio et la vidéo dans la réunion. L’audio permet aux participants de communiquer entre eux comme s’ils se trouvaient dans la même pièce. La vidéo active l’affichage vidéo dans le client Skype entreprise des participants ou des présentateurs qui rejoignent la réunion avec une webcam ou un appareil de conférence qui prend en charge la vidéo.
  
 Skype entreprise Server offre plusieurs fonctionnalités que les utilisateurs peuvent utiliser pour configurer l’expérience de conférence audio pour l’utilisateur, notamment les suivantes :
  
- **Audience muette.** Le présentateur peut utiliser ce paramètre pour désactiver le micro de tous les participants audio de la conférence et placer celle-ci dans un état où les personnes qui ne sont pas des présentateurs ne peuvent pas réactiver leur micro.
    
- **Annonces d’entrée/sortie de conférence.** Si vous avez activé la conférence rendez-vous, les présentateurs peuvent utiliser ce paramètre pour activer ou désactiver les annonces d’entrée et de sortie afin de limiter les distractions durant une conférence.
    
- **Ajout d’un utilisateur en appelant.** Les présentateurs et les participants qui bénéficient d’une autorisation peuvent ajouter des numéros RTC aux conférences et faire en sorte que la Conférence rende les numéros de téléphone.
    
  Skype entreprise Server offre plusieurs fonctionnalités que les utilisateurs peuvent utiliser pour configurer l’expérience de conférence vidéo pour l’utilisateur, notamment les suivantes :
  
- **Vue de la Galerie.** Dans les visioconférences qui comportent plus de deux personnes, les utilisateurs voient automatiquement tous les participants à la conférence. Si celle-ci comporte plus de cinq participants, la vidéo des participants les plus actifs apparaît sur la ligne supérieure et seule la photo apparaît pour les autres participants. La vidéo à plusieurs est activée par défaut.
    
- **Vidéo panoramique.** Si un périphérique de visioconférence RoundTable est installé dans la salle de conférence, cette fonctionnalité offre une vue à 360 degrés de la salle de conférence. Le clip vidéo panoramique est disponible uniquement avec les périphériques RoundTable.
    
- **Mode vidéo présentateur uniquement.** Les présentateurs peuvent configurer la réunion de sorte que seule la vidéo du présentateur soit affichée. Ceci empêche toute distraction lors des réunions à grande échelle, lorsque plusieurs flux vidéo sont disponibles et verrouillés à différentes sources. Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable.
    
- **Projecteur vidéo.** Les présentateurs peuvent configurer la réunion de sorte que seule la vidéo d’un participant sélectionné qui est une source vidéo soit visible par les autres participants à la conférence. Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable pour la vidéo panoramique.
    
### <a name="dial-in-conferencing"></a>Conférence rendez-vous

La Conférence rendez-vous permet aux participants d’une réunion de participer à la partie audio d’une réunion en appelant la réunion à partir d’un téléphone. Une conférence rendez-vous est un sous-ensemble d’une audioconférence et nécessite une configuration supplémentaire. Pour plus d’informations sur les conférences rendez-vous, reportez-vous à la rubrique [plan for Dial-in Conferencing in Skype for Business Server](dial-in-conferencing.md) et [configure Dial-in Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conférence de messagerie instantanée

La fonctionnalité de conférence par messagerie instantanée permet à plus de deux parties de communiquer dans une seule session de messagerie instantanée. Pour plus d’informations sur les conférences de messagerie instantanée, voir [plan for Instant Messaging and Presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Composants de conférence

Les composants qui prennent en charge les fonctionnalités de conférence sont les suivants :
  
- **Service d’application.** Le service d’application fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées. La Conférence rendez-vous utilise deux applications de communications unifiées qui nécessitent le service d’application : annonce du surveillant de conférence et de la Conférence. Le service d’application est installé et activé par défaut sur chaque serveur frontal dans un pool frontal. Il est également installé sur chaque serveur Standard Edition pour activer et configurer la Conférence rendez-vous.
    
- **Application de surveillance de conférence.** L’application de surveillance de conférence est une application de communications unifiées qui accepte les appels PSTN (réseau téléphonique commuté), lance des invites et joint les appels à une conférence A/V. L’application de surveillance de conférence est installée et activée par défaut lorsque vous activez la Conférence rendez-vous.
    
- **Application d’annonce de conférence.** L’application d’annonce de conférence est une application de communications unifiées qui lit des tonalités et des invites aux participants PSTN sur certaines actions, par exemple lorsque des participants rejoignent ou quittent une conférence, les participants sont activés ou désactivés, une personne entre dans la salle d’attente ou la Conférence est verrouillée ou déverrouillée. L’application d’annonce de conférence prend également en charge les commandes de numérotation en fréquences vocales (DTMF) à partir du clavier du téléphone. L’application d’annonce de conférence est automatiquement installée et activée par défaut lorsque vous activez la Conférence rendez-vous.
    
- **Page Paramètres de conférence rendez-vous.** La page Paramètres de conférence rendez-vous affiche les numéros de téléphone de conférence avec leurs langues disponibles, les informations de conférence affectées (c’est-à-dire, pour les réunions qui n’ont pas besoin d’être planifiées) et les contrôles DTMF de conférence, et prend en charge la gestion des informations sur les conférences et les numéros de conférence. La page Paramètres de conférence rendez-vous est automatiquement installée dans le cadre des services Web.
    
- **Serveur de médiation et passerelle PSTN.** La Conférence rendez-vous nécessite un serveur de médiation pour traduire la signalisation (et les médias dans certaines configurations) entre Skype entreprise Server et la passerelle PSTN, ainsi qu’une passerelle PSTN pour traduire la signalisation et les médias entre le serveur de médiation et la passerelle PSTN. Pour la Conférence rendez-vous, vous devez déployer au moins un serveur de médiation et au moins l’un des éléments suivants :
    
  - Passerelle PSTN
    
  - IP-PBX
    
  - Contrôleur de frontière de session (SBC) (pour un fournisseur de services de téléphonie Internet auquel vous vous connectez en configurant une jonction SIP)
    
  > [!NOTE]
  > Si vous déployez également voix entreprise, le serveur de médiation et les passerelles RTC font partie du déploiement voix entreprise. Si vous déployez pas Voix Entreprise, vous devez déployer au moins un serveur de médiation et une passerelle PSTN, un système IP-PBX ou un contrôleur de frontière de session pour la conférence rendez-vous. 
  
- **Magasin de fichiers.** Le magasin de fichiers est utilisé pour le nom enregistré des fichiers audio. Le magasin de fichiers est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.
    
- **Magasin d’utilisateurs.** Le magasin d’utilisateurs est utilisé pour stocker les codes confidentiels Skype entreprise Server de l’utilisateur. Les codes confidentiels sont hachés. Le magasin d’utilisateurs est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.
    
- **Office Web Apps Server.** Pour pouvoir utiliser les fonctionnalités de conférence Web, les administrateurs doivent installer Office Web Apps Server et configurer Skype entreprise Server pour qu’ils communiquent avec Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Stratégies de conférence

Pour appliquer les stratégies de votre organisation et contrôler l’utilisation de la bande passante, vous pouvez définir des stratégies pour les types de réunions que les utilisateurs peuvent organiser. Vous pouvez définir un grand nombre de stratégies de conférence et les affecter à des utilisateurs individuels et à des groupes d’utilisateurs. Vous pouvez également définir des stratégies régissant les conversations d’égal à égal. Pour plus d’informations sur la définition des stratégies de conférence, voir [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Pour plus d’informations sur la gestion de la bande passante, voir [plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Prise en charge des grandes réunions

La taille des réunions que Skype entreprise Server peut prendre en charge dépend du fait que la Conférence est hébergée sur un pool partagé ou dédié :
  
- Dans un pool partagé, Skype entreprise Server peut héberger des réunions avec un maximum de 250 utilisateurs. Un pool partagé est un pool qui héberge toutes les charges de travail Skype entreprise Server, y compris la messagerie instantanée et la présence, les conférences et voix entreprise. 
    
- Dans un pool dédié, Skype entreprise Server peut prendre en charge des réunions avec un maximum de 1000 participants à l’aide de conférences Web et audio/vidéo (A/V), y compris le partage de présentations PowerPoint. Cette prise en charge requiert un pool dédié configuré pour prendre en charge de grandes réunions et géré pour n’héberger qu’une seule grande réunion à la fois. 
    
Pour plus d’informations sur la gestion des grandes réunions, voir [plan for large meetings in Skype for Business Server](large-meetings.md).
  
Si votre organisation requiert des capacités de réunion plus importantes, vous devez envisager d’implémenter un environnement hybride qui tire parti de la diffusion de réunion Skype, un service en ligne qui fait partie de Microsoft 365 et Office 365. La diffusion de réunion Skype permet aux utilisateurs d’héberger et de diffuser des réunions à un grand public en ligne, jusqu’à 10 000 participants. L’utilisation de la diffusion de réunion Skype nécessite que Skype entreprise Server soit déjà configuré dans une configuration hybride avec une organisation Microsoft 365 ou Office 365 de production. Tous les utilisateurs doivent disposer d’un client en ligne établi en tant que composant requis. Si vous souhaitez déployer une solution hybride pouvant tirer parti de la diffusion de réunion Skype, reportez-vous à [la rubrique Configure Your on-premises Deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Déterminer les besoins de votre organisation

Lorsque vous déterminez les fonctionnalités de conférence à déployer, vous devez tenir compte des fonctionnalités que vous souhaitez mettre à disposition de vos utilisateurs et des capacités de votre bande passante réseau. La liste suivante vous guide tout au long du processus de planification de la Conférence afin de déterminer les fonctionnalités de conférence que vous devez déployer, en fonction des besoins de votre organisation.
  
> [!NOTE]
> Lorsque vous activez la Conférence lors du déploiement, vous activez automatiquement les conférences Web et A/V. Toutefois, vous pouvez désactiver des fonctionnalités spécifiques en configurant des stratégies de conférence, comme décrit précédemment dans cette rubrique. 
  
- **Souhaitez-vous activer la conférence web, qui inclut la collaboration sur des documents et le partage d’application ?**
    
    Si c’est le cas, vous devez activer la Conférence pour votre pool frontal à l’aide de l’outil de planification ou du générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Le partage d’application requiert et utilise plus de bande passante réseau que la collaboration sur des documents. Skype entreprise Server fournit un mécanisme de limitation pour contrôler chaque session de partage d’application. Par défaut, il est défini à 1,5 Ko/seconde pour chaque session. Si vous ne souhaitez pas activer le partage d’application, mais que vous souhaitez collaborer sur des documents, vous pouvez activer la Conférence et utiliser des stratégies de conférence pour désactiver le partage d’application. Pour plus d’informations sur la configuration des stratégies de conférence, voir [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Pour permettre aux utilisateurs de partager des présentations PowerPoint, vous devez configurer Office Web Apps Server. Pour plus d’informations sur la configuration d’Office Web Apps Server, consultez la rubrique [configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Voulez-vous activer la fonctionnalité de conférence audio et vidéo ?**
    
    Si c’est le cas, vous devez activer la Conférence pour votre pool frontal à l’aide de l’outil de planification ou du générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    La conférence audio et vidéo nécessite et utilise plus de bande passante réseau que la conférence Web (ce qui inclut la collaboration sur les documents et le partage d’applications). Si vous ne souhaitez pas activer la conférence audio et vidéo, mais que vous voulez activer la conférence Web, vous pouvez activer la Conférence et utiliser des stratégies de conférence pour désactiver les conférences A/V.
    
    Si vous souhaitez activer les conférences audio mais pas les vidéoconférences, vous pouvez activer la conférence A/V et utiliser des stratégies de conférence pour empêcher les vidéoconférences. De même, vous pouvez activer la conférence A/V, et autoriser uniquement certains utilisateurs à initier une conférence A/V ou à y prendre part. 
    
    Pour plus d’informations sur la configuration des stratégies de conférence, voir [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Voix entreprise n’est pas nécessaire pour utiliser la conférence A/V. Si vous activez la conférence A/V, vos utilisateurs peuvent ajouter de l’audio à leurs conférences pourvu qu’ils disposent de périphériques audio, et ce même si vous utilisez un autocommutateur privé (PBX) pour votre solution téléphonique. 
  
- **Souhaitez-vous autoriser les utilisateurs à participer à la partie audio des conférences lorsqu’ils utilisent un téléphone PSTN ?**
    
    Dans l’affirmative, déployez et activez la conférence rendez-vous. Les utilisateurs invités, à l’intérieur et à l’extérieur de votre organisation, peuvent alors prendre part à la partie audio des conférences par l’intermédiaire d’un téléphone PSTN.
    
    La Conférence rendez-vous est une fonctionnalité facultative que vous pouvez configurer lorsque vous déployez Skype entreprise Server Conferencing. Bien que la Conférence rendez-vous utilise certains des mêmes composants que voix entreprise, vous pouvez déployer la Conférence rendez-vous même si vous ne déployez pas voix entreprise. La Conférence rendez-vous prend en charge les utilisateurs d’entreprise et les utilisateurs anonymes. Pour plus d’informations sur la configuration de la Conférence rendez-vous pour les utilisateurs d’entreprise et les utilisateurs anonymes, voir [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) et [configure Dial-in Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Souhaitez-vous autoriser les utilisateurs externes avec des clients Skype entreprise à participer à des conférences ?**
    
    En autorisant une participation externe aux réunions, vous optimisez votre investissement dans Skype entreprise Server. Les utilisateurs externes peuvent inclure les catégories suivantes :
    
  - **Utilisateurs distants.** Les utilisateurs de votre organisation, lorsqu’ils travaillent à l’extérieur de vos pare-feu et qu’ils utilisent leur ordinateur portable ou d’autres appareils Skype entreprise Server.
    
  - **Utilisateurs fédérés.** Les utilisateurs des entreprises avec lesquelles vous travaillez et qui exécutent également Skype entreprise Server. Pour autoriser vos utilisateurs à contacter facilement ces utilisateurs, créez des relations fédérées avec ces entreprises.
    
  - **Utilisateurs anonymes.** Tous les autres utilisateurs externes qui sont invités par vos utilisateurs à participer à des conférences spécifiques. Un organisateur de réunion qui appartient à votre entreprise peut envoyer à un utilisateur externe, par courrier électronique, une invitation à participer à une conférence. Le courrier électronique inclut un lien sur lequel l’utilisateur externe peut cliquer pour prendre part à la conférence.
    
    Si vous souhaitez autoriser les utilisateurs externes, vous devez déployer les serveurs Edge. De plus, avec les serveurs Edge déployés, vous pouvez créer des relations fédérées avec d’autres organisations, telles que vos clients ou fournisseurs, et les utilisateurs de ces organisations peuvent plus facilement collaborer avec vos utilisateurs.
    
    Pour plus d’informations sur le déploiement des serveurs Edge, reportez-vous à la rubrique plan for Edge Servers et deploy Edge Servers. Pour plus d’informations sur l’activation de l’accès externe pour Office Web Apps Server, consultez la rubrique [configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Souhaitez-vous contrôler les clients qui peuvent participer à des réunions Skype entreprise Server ?**
    
    Dans l’affirmative, vous devez configurer la page de participation aux réunions, afin que seules les options clientes que vous souhaitez prendre en charge soient disponibles. Chaque fois qu’un utilisateur clique sur un lien pour participer à une réunion planifiée, Skype entreprise Server détecte si un client est déjà installé sur l’ordinateur. Il démarre alors le client par défaut et ouvre la page de participation à la réunion qui contient des liens vers d’autres clients. La page de participation aux réunions contient toujours la possibilité d’utiliser Skype entreprise Web App. En plus de cette option, vous pouvez décider s’il faut inclure des liens pour les participants et les versions précédentes de Communicator. 
    

