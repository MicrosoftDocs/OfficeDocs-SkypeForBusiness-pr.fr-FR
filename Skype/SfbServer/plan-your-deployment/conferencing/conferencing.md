---
title: Planifier des conférences dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Résumé: cette rubrique vous permet d’en savoir plus sur les fonctionnalités et capacités de conférence dans Skype entreprise Server.'
ms.openlocfilehash: 9b46271e4381e2d2e11f00e3d936660626fbe5cf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277355"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planifier des conférences dans Skype entreprise Server
 
**Résumé:** Consultez cette rubrique pour en savoir plus sur les fonctionnalités et capacités de conférence dans Skype entreprise Server.
  
Les conférences dans Skype entreprise Server permettent aux utilisateurs de se réunir et de tenir des conférences en ligne à l’aide de leur client Skype entreprise au lieu de se réunir dans la même pièce. Les participants à la réunion peuvent se connecter à une réunion à l’aide de leur client Skype entreprise pour une utilisation complète de l’audio et de la vidéo, ou se connecter à une conférence à l’aide d’un téléphone. Les conférences prennent également en charge la messagerie instantanée, le partage du bureau et des applications, ainsi que les tableaux blancs interactifs.
  
Cette rubrique inclut les sections suivantes :
  
- Fonctionnalités et fonctions de conférence
    
- Composants de conférence
    
- Stratégies de conférence
    
- Prise en charge de grandes réunions
    
- Détermination des besoins de votre organisation
    
## <a name="conferencing-features-and-capabilities"></a>Fonctionnalités et fonctions de conférence

Il existe quatre types de conférences disponibles dans Skype entreprise Server: les conférences Web, les conférences audio et vidéo (A/V), les conférences rendez-vous et les conférences de messagerie instantanée. 
  
Vous pouvez choisir d’activer tous les types de conférence ou d’utiliser un seul type, selon vos besoins. Par exemple, vous pouvez activer tous les types, y compris les conférences rendez-vous, pour permettre aux utilisateurs qui ne peuvent pas participer à une conférence avec un client Skype entreprise d’appeler le son de la réunion à partir d’un téléphone et de participer à celle-ci. Lorsque vous déployez Skype entreprise Server, les fonctionnalités de conférence par messagerie instantanée sont déployées automatiquement. vous pouvez spécifier si vous souhaitez déployer le Web, A/V et la Conférence rendez-vous à l’aide du générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique [déploiement de conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
Les sous-sections ci-dessous décrivent les fonctionnalités et les fonctions de chaque type de conférence.
  
### <a name="web-conferencing"></a>Conférence web

Les conférences Web permettent aux participants d’une réunion de collaborer sur des documents partagés pendant la réunion et de partager des applications avec le client Skype entreprise. La conférence web offre les fonctionnalités suivantes : 
  
- **Tableau blanc et annotations.** Un tableau blanc est une surface vierge qui vous permet de collaborer en utilisant du texte, des entrées manuscrites, des dessins et des images. Tous les participants à une réunion peuvent voir les annotations qui y sont ajoutées. La fonctionnalité de tableau blanc favorise la collaboration en permettant aux participants à une réunion d’échanger des idées, de débattre, de prendre des notes, etc.
    
- **Interrogation.** La fonctionnalité sondage améliore la collaboration en permettant aux présentateurs de déterminer rapidement les préférences des participants. Lors des réunions et des conversations en ligne, les présentateurs peuvent avoir recours à l’interrogation pour recueillir des réponses anonymes des participants. Tous les présentateurs peuvent voir les résultats et choisir de les montrer à tous les participants ou de les masquer.
    
- **Partage d’application et partage de bureau.** Au cours d’une conférence, le présentateur de la réunion peut partager son bureau complet, une application individuelle ou des écrans individuels dans un environnement multi-moniteur. Les autres participants à la conférence peuvent non seulement afficher le contenu, mais également demander le contrôle de l’écran du présentateur et, grâce à cette autorisation, interagir avec le contenu (dont le défilement et l’édition). Les participants aux réunions peuvent également endosser le rôle de présentateur et commencer à partager du contenu lors de la réunion.
    
- **Partage de PowerPoint.** Permet aux utilisateurs de partager des présentations PowerPoint dans la réunion par le biais d’un serveur Office Web Apps, qui offre les possibilités suivantes :
    
  - Résolution d’affichage supérieure et prise en charge des fonctions de PowerPoint, comme les animations, les transitions de diapositives et la vidéo incorporée.
    
  - Présentations accessibles à un grand nombre d’appareils mobiles.
    
  - Possibilité pour les utilisateurs disposant des autorisations appropriées de parcourir librement une présentation PowerPoint indépendamment de la présentation proprement dite. Par exemple, pendant que Ken présente son diaporama, Heidi peut visualiser la diapositive de son choix sans perturber la présentation de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conférence audio et vidéo

La conférence audio et vidéo permet d’utiliser du son et de la vidéo pendant la réunion. L’audio permet aux participants de communiquer entre eux comme s’ils se trouvaient dans la même pièce. La vidéo permet l’affichage vidéo dans le client Skype entreprise de tout participant ou présentateur qui participe à la réunion à l’aide d’une webcam ou d’un appareil de visioconférence prenant en charge la vidéo.
  
 Skype entreprise Server offre plusieurs fonctionnalités que les utilisateurs peuvent utiliser pour configurer l’utilisation de l’audioconférence pour l’utilisateur, notamment les suivantes:
  
- **Désactiver le son pour les participants.** Le présentateur peut utiliser ce paramètre pour désactiver le micro de tous les participants audio de la conférence et placer la conférence dans un état dans lequel seuls les présentateurs peuvent réactiver le micro des participants.
    
- **Annonce d’entrée/sortie de conférence.** Si vous avez activé la conférence rendez-vous, les présentateurs peuvent utiliser ce paramètre pour activer ou désactiver les annonces d’entrée et de sortie afin de limiter les distractions durant une conférence.
    
- **Ajouter un utilisateur en composant un numéro de téléphone.** Les présentateurs et les participants qui ont reçu une autorisation peuvent ajouter des numéros RTC aux conférences et être disposant d’une conférence rendez-vous pour ces numéros.
    
  Skype entreprise Server offre plusieurs fonctionnalités que les utilisateurs peuvent utiliser pour configurer l’interface de visioconférence pour l’utilisateur, notamment les suivantes:
  
- **Affichage Galerie.** Dans les visioconférences qui incluent plus de deux personnes, les utilisateurs voient automatiquement tous les participants à la conférence. Si la conférence rassemble plus de cinq participants, la vidéo des participants les plus actifs s’affiche sur la ligne supérieure et seule la photo s’affiche pour les autres participants. La vidéo à plusieurs est activée par défaut.
    
- **Vidéo panoramique.** Si un appareil de visioconférence RoundTable est installé dans la salle de conférence, cette fonctionnalité offre une vue à 360 degrés de la salle de conférence. Le clip vidéo panoramique n’est disponible qu’avec les appareils RoundTable.
    
- **Mode vidéo du présentateur uniquement.** Les présentateurs peuvent configurer la réunion de manière à n’afficher que la vidéo du présentateur. Cela empêche toute distraction lors de grandes réunions, lorsque plusieurs flux vidéo sont disponibles et verrouillés à différentes sources. Ce mode s’applique également à la vidéo capturée et fournie par les appareils RoundTable.
    
- **Actualités vidéo.** Les présentateurs peuvent configurer la réunion de manière à n’afficher que la vidéo d’un participant sélectionné, qui est une source vidéo, pour les autres participants à la conférence. Ce mode s’applique également à la vidéo capturée et fournie par les appareils RoundTable pour la vidéo panoramique.
    
### <a name="dial-in-conferencing"></a>Conférence rendez-vous

Les conférences rendez-vous permettent aux participants d’une réunion de rejoindre la partie audio d’une réunion en appelant la réunion à partir d’un téléphone. Une conférence rendez-vous est un sous-ensemble d’une conférence audio nécessitant une configuration supplémentaire. Pour plus d’informations sur les conférences rendez-vous, reportez-vous à la rubrique [planification de conférences rendez-vous dans Skype entreprise Server](dial-in-conferencing.md) et [configuration de conférences rendez-vous dans Skype entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conférence par messagerie instantanée

La conférence par messageries instantanée (MI) permet à au moins deux parties de communiquer lors d’une session de messagerie instantanée. Pour plus d’informations sur les conférences de messagerie instantanée, reportez-vous à la rubrique [planification de la messagerie instantanée et de la présence dans Skype entreprise Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Composants de conférence

Les composants prenant en charge les fonctionnalités de conférence sont les suivants :
  
- **Service d’application.** Le service d’application permet à une plate-forme de déployer, d’héberger et de gérer des applications de communications unifiées. La conférence rendez-vous utilise deux applications de communications unifiées nécessitant le service d’application : Intendant Conférence et Annonce de conférence. Le service d’application est installé et activé par défaut sur chaque serveur frontal d’une liste frontale. Il est également installé sur chaque serveur Standard Edition pour activer et configurer la fonctionnalité de conférence rendez-vous.
    
- **Application Intendant Conférence.** L’application Intendant Conférence est une application de communications unifiées qui accepte les appels sur le réseau téléphonique commuté (RTC), affiche des invites et associe les appels à une conférence audio/vidéo. L’application Intendant Conférence est installée et activée par défaut lorsque vous activez la conférence rendez-vous.
    
- **Application Annonce de conférence.** Cette application de communications unifiées joue des tonalités et des invites aux participants RTC lors de certaines actions, par exemple, lorsque les participants rejoignent une conférence ou la quittent, lorsque le micro des participants est coupé ou rétabli, lorsque quelqu’un entre dans la salle d’attente ou lorsque la conférence est verrouillée ou déverrouillée. L’application Annonce de conférence prend également en charge les commandes de numérotation à fréquences vocales (DTMF) à partir du clavier du téléphone. L’application d’annonce de conférence est installée et activée automatiquement par défaut lorsque vous activez la conférence rendez-vous.
    
- **Page Paramètres de conférence rendez-vous.**  La page Paramètres de conférence rendez-vous indique les numéros d’accès aux conférences et les langues dans lesquelles ils sont disponibles. Elle présente également les informations relatives aux conférences affectées aux utilisateurs (c’est-à-dire pour les réunions qui ne doivent pas être planifiées) et comporte des contrôles DTMF à utiliser en cours de conférence. Enfin, elle permet aux utilisateurs de gérer leur code confidentiel et les informations relatives aux conférences qui leur ont été affectées. La page Paramètres de conférence rendez-vous est installée automatiquement dans le cadre des services web.
    
- **Serveur de médiation et passerelle RTC.** La Conférence rendez-vous nécessite un serveur de médiation pour traduire la signalisation (et les éléments multimédias dans certaines configurations) entre Skype entreprise Server et la passerelle RTC et une passerelle PSTN pour traduire les signaux et les médias entre le serveur de médiation et la passerelle PSTN. . Pour les conférences rendez-vous, vous devez déployer au moins un serveur de médiation et au moins l’un des éléments suivants:
    
  - Passerelle RTC
    
  - IP-PBX
    
  - Contrôleur SBC (Session Border Controller) (pour un fournisseur de services de téléphonie Internet sur lequel vous vous connectez en configurant une jonction SIP [Session Initiation Protocol])
    
  > [!NOTE]
  > Si vous déployez également Enterprise Voice, les passerelles RTC et serveur de médiation font partie du déploiement voix entreprise. Si vous ne déployez pas l’entreprise voix, vous devez déployer au moins un serveur de médiation et au moins une passerelle RTC, un PBX IP ou un SBC pour la Conférence rendez-vous. 
  
- **Magasin de fichiers.** Le magasin de fichiers est utilisé pour le nom enregistré des fichiers audio. Le magasin de fichiers est un composant standard dans chaque déploiement Entreprise ou Standard.
    
- **Magasin d’utilisateurs.** Le magasin des utilisateurs est utilisé pour stocker les codes confidentiels de l’utilisateur Skype entreprise Server. Les codes confidentiels sont hachés. Le magasin d’utilisateurs est un composant standard dans chaque déploiement Entreprise ou Standard.
    
- **Serveur Office Web Apps.** Pour pouvoir utiliser les fonctionnalités de conférence Web, les administrateurs doivent installer Office Web Apps Server et doivent configurer Skype entreprise Server pour communiquer avec Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Stratégies de conférence

Pour appliquer les stratégies de votre organisation et contrôler l’utilisation de la bande passante, vous pouvez définir des stratégies pour les types de réunions que les utilisateurs peuvent organiser. Vous pouvez définir un grand nombre de stratégies de conférence et les affecter à des utilisateurs et à des groupes d’utilisateurs spécifiques. Vous pouvez également définir des stratégies régissant les conversations P2P. Pour plus d’informations sur la configuration des stratégies de conférence, voir [gérer les stratégies de conférence dans Skype entreprise Server](../../manage/conferencing/conferencing-policies.md). Pour plus d’informations sur la gestion de la bande passante, voir [planifier le contrôle d’admission des appels dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Prise en charge de grandes réunions

La taille des réunions prises en charge par Skype entreprise Server varie selon que les conférences sont hébergées sur un pool partagé ou dédié:
  
- Sur une réserve partagée, Skype entreprise Server peut héberger des réunions avec des utilisateurs de 250 maximum. Un pool partagé est un pool qui héberge toutes les charges de travail du serveur Skype entreprise, notamment la messagerie instantanée (mi) et la présence, les conférences et l’entreprise voix. 
    
- Dans le cas d’une réserve dédiée, Skype entreprise Server peut prendre en charge des réunions avec les 1000 participants au maximum à l’aide de conférences Web et audio/vidéo (A/V), y compris le partage de présentations PowerPoint. Cette prise en charge nécessite un pool dédié configuré pour prendre en charge de grandes réunions et géré pour n’héberger qu’une seule grande réunion à la fois. 
    
Pour plus d’informations sur la gestion des réunions de grande taille, voir [planifier une réunion de grande envergure dans Skype entreprise Server](large-meetings.md).
  
Si votre organisation nécessite une plus grande capacité de réunion, vous devez envisager de mettre en place un environnement hybride qui tire parti de la diffusion de réunion Skype, un service en ligne intégré à Office 365. La diffusion de réunion Skype permet aux utilisateurs d’héberger et de diffuser des réunions à des réunions en ligne comptant jusqu’à 10 000 participants. L’utilisation de la diffusion de réunion Skype exige que Skype Entreprise Server soit déjà configuré dans une configuration hybride avec un client Office 365 de production. Un client en ligne doit être installé au préalable pour tous les utilisateurs. Si vous souhaitez déployer une solution hybride pouvant tirer parti de la diffusion de réunion Skype, reportez-vous à la rubrique [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Détermination des besoins de votre organisation

Lorsque vous déterminez les fonctions de conférence à déployer, vous devez tenir compte des fonctionnalités que vous souhaitez mettre à disposition de vos utilisateurs et des capacités de votre bande passante réseau. La liste suivante vous guide tout au long du processus de planification des conférences afin de déterminer les fonctionnalités de conférence que vous devez déployer en fonction de la configuration requise pour votre organisation.
  
> [!NOTE]
> Lorsque vous activez la conférence lors du déploiement, vous autorisez automatiquement les fonctionnalités de conférence web et A/V. En revanche, vous pouvez désactiver des fonctionnalités spécifiques en configurant des stratégies de conférence, comme indiqué précédemment dans cette rubrique. 
  
- **Souhaitez-vous activer la conférence web, qui inclut la collaboration sur des documents et le partage d’application ?**
    
    Si c’est le cas, vous devez activer la conférence pour votre pool frontal à l’aide de l’outil de planification ou du générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique [déploiement de conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Le partage d’application nécessite et utilise plus de bande passante réseau que la collaboration sur des documents. Skype entreprise Server fournit un mécanisme de limitation pour contrôler chaque session de partage d’application. Par défaut, il est défini à 1,5 Ko/seconde pour chaque session. Si vous ne souhaitez pas activer le partage d’application, mais que vous voulez collaborer sur des documents, vous pouvez activer les conférences et utiliser des stratégies de conférence pour désactiver le partage d’application. Pour plus d’informations sur la configuration des stratégies de conférence, voir [gérer les stratégies de conférence dans Skype entreprise Server](../../manage/conferencing/conferencing-policies.md).
    
    Pour autoriser les utilisateurs à partager des présentations PowerPoint, vous devez configurer Office Web Apps Server. Pour plus d’informations sur la configuration d’Office Web Apps Server, voir [configurer l’intégration avec Office Web Apps Server dans Skype entreprise Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Voulez-vous activer la fonctionnalité de conférence audio et vidéo ?**
    
    Si c’est le cas, vous devez activer la conférence pour votre pool frontal à l’aide de l’outil de planification ou du générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique [déploiement de conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    La conférence audio et vidéo nécessite et utilise plus de bande passante réseau que la conférence web (qui inclut la collaboration sur des documents et le partage d’applications). Si vous ne souhaitez pas activer la conférence audio et vidéo, mais que vous voulez activer la conférence web, vous pouvez activer la fonctionnalité de conférence et utiliser des stratégies de conférence pour désactiver la conférence A/V.
    
    Si vous souhaitez activer la conférence audio, mais pas la conférence vidéo, vous pouvez activer la conférence A/V et utiliser des stratégies de conférence pour interdire la conférence vidéo. De même, vous pouvez activer la conférence A/V et ne permettre qu’à certains utilisateurs de commencer une conférence A/V ou d’y participer. 
    
    Pour plus d’informations sur la configuration des stratégies de conférence, voir [gérer les stratégies de conférence dans Skype entreprise Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Vous n’êtes pas obligé d’utiliser Voix Entreprise pour utiliser la conférence A/V. Si vous activez la conférence A/V, vos utilisateurs peuvent ajouter de l’audio à leurs conférences sous réserve qu’ils disposent de périphériques audio, et ce, même si vous utilisez un autocommutateur privé (PBX) pour votre solution téléphonique. 
  
- **Souhaitez-vous permettre aux utilisateurs d’accéder à la partie audio des conférences lors de l’utilisation d’un téléphone RTC?**
    
    Si c’est le cas, déployez et activez la conférence rendez-vous. Les utilisateurs invités, à l’intérieur et à l’extérieur de votre organisation, peuvent alors participer à la partie audio des conférences par l’intermédiaire d’un téléphone RTC.
    
    La fonction de conférence rendez-vous est une fonctionnalité facultative que vous pouvez configurer lors du déploiement de Skype entreprise Server Conferencing. Même si la conférence rendez-vous utilise une partie des mêmes composants que Voix Entreprise, vous pouvez la déployer même si vous ne déployez pas Voix Entreprise. La fonction de conférence rendez-vous est prise en charge pour les utilisateurs d’entreprise et les utilisateurs anonymes. Pour plus d’informations sur la configuration des conférences rendez-vous pour les utilisateurs d’entreprise et anonymes, reportez-vous à la rubrique [déploiement de conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md) et configuration de conférences rendez [-vous dans Skype entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Souhaitez-vous autoriser les utilisateurs externes disposant de clients Skype Entreprise à participer à des conférences ?**
    
    En autorisant la participation externe aux réunions, vous Maximisez votre investissement dans Skype entreprise Server. Les utilisateurs externes peuvent être les utilisateurs suivants :
    
  - **Utilisateurs distants.** Les utilisateurs propres de votre organisation, lorsqu’ils travaillent à l’extérieur de votre pare-feu et qu’ils utilisent leur ordinateur portable ou d’autres appareils Skype entreprise Server.
    
  - **Utilisateurs fédérés.** Les utilisateurs des entreprises avec lesquelles vous travaillez, qui exécutent également Skype entreprise Server. Pour autoriser vos utilisateurs à communiquer facilement avec ces utilisateurs externes, créez des relations fédérées avec ces entreprises.
    
  - **Utilisateurs anonymes.** Tous les autres utilisateurs externes invités par vos utilisateurs à participer à des conférences spécifiques. Un organisateur de réunion qui appartient à votre entreprise peut envoyer à un utilisateur externe, par courrier électronique, une invitation à participer à une conférence. Le courrier électronique inclut un lien sur lequel l’utilisateur externe peut cliquer pour participer à la conférence.
    
    Si vous voulez autoriser les utilisateurs externes, vous devez déployer des serveurs Edge. De plus, avec les serveurs Edge déployés, vous pouvez créer des relations fédérées avec d’autres organisations (clients ou fournisseurs, par exemple) et d’autres utilisateurs de ces organisations peuvent plus facilement collaborer avec vos utilisateurs.
    
    Pour plus d’informations sur le déploiement de serveurs Edge, reportez-vous aux rubriques Planification des serveurs Edge et Déploiement des serveurs Edge. Pour plus d’informations sur l’activation de l’accès externe pour Office Web Apps Server, voir [configurer l’intégration avec Office Web Apps Server dans Skype entreprise Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Souhaitez-vous contrôler les clients qui peuvent rejoindre des réunions Skype entreprise Server?**
    
    Si c’est le cas, vous devez configurer la page de participation aux réunions de sorte que seules les options du client à prendre en charge soient disponibles. Chaque fois qu’un utilisateur clique sur un lien pour rejoindre une réunion planifiée, Skype entreprise Server détecte si un client est déjà installé sur l’ordinateur. Il lance alors le client par défaut et ouvre la page de participation à la réunion qui contient des liens vers d’autres clients. La page de participation à une réunion contient toujours l’option d’utilisation de Skype entreprise Web App. Outre cette option, vous pouvez décider d’inclure ou non des liens vers Participant et les versions précédentes de Communicator. 
    

