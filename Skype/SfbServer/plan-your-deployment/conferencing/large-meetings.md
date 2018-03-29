---
title: Planification de réunions importantes dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les méthodes conseillées pour la mise en œuvre et la gestion des réunions de grande taille dans Skype pour Business Server 2015.'
ms.openlocfilehash: 6a2af2ef9e7698f9141baf78f99b9bc9febfaa67
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-large-meetings-in-skype-for-business-server-2015"></a>Planification de réunions importantes dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les méthodes conseillées pour la mise en œuvre et la gestion des réunions de grande taille dans Skype pour Business Server 2015.
  
La taille des réunions Skype pour Business Server peut prendre en charge dépend de si la conférence est hébergé sur un pool partagé ou dédié : n’importe où à partir de 250 participants sur un pool partagé aux participants de 1000 sur un pool dédié. 
  
> [!NOTE]
> Cette rubrique met l’accent sur les meilleures pratiques pour les grandes réunions pris en charge par Skype pour Business Server. Si votre organisation requiert des grandes fonctionnalités de réunion, vous devez envisager d’implémenter un environnement hybride qui tire parti de la diffusion de réunion Skype, un nouveau service en ligne qui fait partie d’Office 365. 

> [!NOTE]
> La diffusion de réunion Skype permet aux utilisateurs d’héberger et de diffuser des réunions à des réunions en ligne comptant jusqu’à 10 000 participants. L’utilisation de la diffusion de réunion Skype exige que Skype Entreprise Server soit déjà configuré dans une configuration hybride avec un client Office 365 de production. Un client en ligne doit être installé au préalable pour tous les utilisateurs. Si vous êtes intéressé par le déploiement d’une solution hybride qui peut tirer parti de la diffusion de réunion Skype, consultez [ce qu’est une diffusion de réunion Skype ?](https://go.microsoft.com/fwlink/?LinkId=617071) et [configurer votre déploiement sur site de diffusion de réunion Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Les grandes réunions possèdent généralement les caractéristiques suivantes :
  
- Le format de la réunion est celui d’une présentation un-à-plusieurs.
    
- Un ou plusieurs utilisateurs sont des présentateurs. Le reste de l’assistance sont des participants.
    
- Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.
    
- L’audio est nécessaire et la vidéo peut également être utilisée.
    
- Une personne dédiée, généralement l’organisateur de la réunion ou un assistant de l’organisateur, prépare la réunion à l’avance.
    
- Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, de façon appropriée.
    
Lorsqu’un utilisateur planifie une réunion, Skype pour Business Server crée un enregistrement dans la base de données de conférence, qui stocke les données de conférence, mais ne réserve pas les ressources de matériel pour la réunion planifiée à l’avance. Au lieu de cela, Skype pour Business Server a une logique pour allouer dynamiquement des ressources de la conférence sur les serveurs frontaux d’une façon qui répartit les charges équitablement sur tous les serveurs frontaux dans le pool d’équilibrage de la charge intégrée. Cela permet de mettre en service et d’utiliser des ressources matérielles, mais il est important de prévoir correctement la prise en charge des réunions de très grande taille. 
  
Par exemple, lorsqu’un Skype pour le pool de serveur d’entreprise s’exécute proche de sa capacité maximale, chaque serveur frontal peut héberger environ 125 réunions de taille moyenne. L’ajout d’une autre réunion de petite taille ne serait pas un obstacle à la différence d’une réunion de 1 000 utilisateurs, car les serveurs frontaux ne pourraient probablement pas prendre en charge une grande réunion en même temps que les 125 autres réunions.
  
La prise en charge de réunions de grande taille (1 000 participants) nécessite de régler les aspects liés à la fois au modèle matériel partagé et au modèle d’absence de réservation. En règle générale, vous devez prévoir un pool dédié et suivent les meilleures pratiques, comme décrit dans les sections suivantes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planification d’un pool dédié

Si votre organisation a besoin de réunions de plus de 250 participants, vous devez planifier un pool dédié pour prendre en charge cette capacité. 
  
Pour disposer de suffisamment de ressources aux niveaux du processeur et de la mémoire pour les réunions incluant jusqu’à 1 000 utilisateurs, les serveurs frontaux d’hébergement ne doivent pas gérer de fonctionnalités de messagerie instantanée et de présence, ni de charges de travail liées à Voix Entreprise. Ils ne doivent pas non plus héberger d’autres réunions, quelles que soient leurs tailles. Pour héberger des réunions de jusqu'à 1000 utilisateurs, vous devez configurer un Skype distincte pour le pool de serveur d’entreprise dédié à l’hébergement de réunions de grande taille.
  
Un Skype pour le pool de serveur d’entreprise dédié à l’hébergement de réunions de grande taille doit héberger une et une seule réunion jusqu'à 1000 utilisateurs en même temps, donc aux heures de réunion doivent être réservés à l’avance par le biais d’une sortie de bande de planification de processus afin de garantir la prise en charge dédiée à partir de la Serveurs frontaux. Pour prendre en charge plus d’une grande réunion en même temps, vous devez configurer plusieurs pools réunion dédiées.
  
Pour plus d’informations sur le matériel et les logiciels et planification une topologie que prend en charge les réunions volumineux, voir [configuration matérielle et logicielle pour les conférences dans Skype pour Business Server 2015](hardware-and-software-requirements.md) et [planifier votre topologie de conférence pour Skype pour Business Server 2015](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Mise en œuvre des meilleures pratiques pour les grandes réunions

Après avoir configuré un pool dédié pour les grandes réunions, vous pouvez suivre une procédure permettant de garantir que les grandes réunions hébergées dans le pool offrent une expérience utilisateur optimale. Les rubriques de cette section donnent des informations sur la gestion de grandes réunions :
  
- Création d’organisateurs de réunion dédiés
    
- Création de modérateurs dédiés
    
- Gestion d’un calendrier distinct des grandes réunions
    
- Mise en œuvre d’une procédure/// de planification des grandes réunions
    
- Spécification des détails de planification appropriés
    
- Création d’une stratégie de conférence pour les grandes réunions
    
### <a name="create-dedicated-meeting-organizers"></a>Création d’organisateurs de réunion dédiés

Pour réduire le trafic des communications en temps réel dans le pool de grande réunion, Microsoft ne recommande pas l’hébergement des utilisateurs qui régulièrement de se connecter à l’aide de Skype pour les clients de l’entreprise et de participer à la messagerie instantanée (MI), de présence, de conférence et de sessions de voix. Il est préférable de suivre les étapes suivantes :
  
- Création d’un ou de plusieurs comptes d’utilisateur dédiés à la planification des grandes réunions
    
- Hébergement des comptes d’utilisateur du personnel responsable de la planification des grandes réunions dans un pool de grandes réunions
    
### <a name="create-dedicated-moderators"></a>Création de modérateurs dédiés

Les réunions pouvant inclure de plusieurs centaines à un millier d’utilisateurs, il est recommandé de désigner une personne dédiée chargée d’animer la session en ligne d’une grande réunion. Cette personne dédiée peut être un délégué de l’organisateur de la réunion ou d’un membre-réunion de l’organisation personnel de support. Il est important d’ajouter le modérateur de réunion dédié comme présentateur au moment où la réunion est programmée, même s’il soit possible de promouvoir un participant de la réunion en ligne au rôle de présentateur pendant la réunion.
  
Le modérateur de réunion permet de gérer la grande réunion toutes les fonctionnalités de présentateur de Skype pour les clients de l’entreprise. Ces fonctionnalités sont les suivantes :
  
- Surveillance de la salle d’attente et l’admission ou le rejet des utilisateurs dans la salle d’attente
    
- Suppression des utilisateurs qui ne doivent pas participer à la réunion
    
- Modification des types d’accès à la réunion
    
- Modification des rôles des participants
    
- Invitation de participants supplémentaires pendant la réunion à l’aide de la fonction glisser-déplacer de Lync, d’un appel téléphonique ou d’un message électronique
    
- Activation et désactivation du micro du public ou des utilisateurs individuels
    
- Gestion du contenu de réunion, dont le téléchargement de contenu, la suppression du contenu et le basculement du contenu actif
    
### <a name="maintain-a-separate-calendar"></a>Gestion d’un calendrier distinct

Pour chaque pool de réunions de grande taille, vous devriez gérer un calendrier distinct des réunions de grande taille planifiées dans le pool. Par exemple, vous pouvez un seul compte d’utilisateur sur le pool de grande réunion d’accueil et utiliser Outlook avec Exchange et complément de réunion en ligne pour Skype pour les entreprises à gérer un calendrier distinct. Si vous utilisez plusieurs comptes d’utilisateurs pour permettre au support technique de créer des réunions de grande taille, vous pouvez configurer un calendrier distinct qui regroupe toutes les réunions de grande taille créées par les membres du personnel de support technique. 
  
La gestion d’un calendrier distinct des réunions de grande taille contribue à éviter les conflits et permet de s’assurer que seule une réunion de grande taille est active à un moment donné.
  
### <a name="implement-a-scheduling-process"></a>Mise en œuvre d’une procédure de planification

Dans la mesure où une seule réunion à la fois est prise en charge sur le pool de réunion dédiée, vous devez implémenter une grande réunion processus pour faciliter la configuration des réunions volumineuses et d’éviter des conflits de planification. Cette fonctionnalité n’est pas fournie directement par Skype pour Business Server ou Skype pour les clients de l’entreprise. Une façon d’implémenter un tel processus est d’utiliser le système de gestion des tickets de l’équipe de support technique de votre organisation, si disponible.
  
La planification d’une grande réunion implique de suivre la procédure suivante :
  
- Outre la liste de présentateurs, l’organisateur de réunion ou le délégué détermine l’heure, la durée et la taille d’une prochaine réunion. Si la taille de réunion prévue dépasse 250 utilisateurs ou pour garantir la meilleure expérience pour une réunion de moins de 250 utilisateurs, l’organisateur ou le délégué envoie une demande pour une grande réunion.
    
- Le personnel chargé de la planification vérifie si la date et l’heure demandées sont disponibles. Comme nous ne prenons en charge qu’une seule grande réunion à la fois sur le pool dédié, le personnel de planification doit vérifier le calendrier des grandes réunions pour déterminer si une autre réunion est planifiée à la date et à l’heure demandées. Si l’heure demandée est disponible, le personnel approuve la demande de réunion.
    
- Si la demande est approuvée, le personnel de planification (à l’aide des informations d’identification sur le pool dédié) utilise complément de réunion en ligne pour Skype pour entreprise avec Outlook pour configurer une réunion sur le pool de grande réunion dédié. L’URL à utiliser pour participer à la réunion est fournie par le demandeur dans le cadre de l’avis d’approbation.
    
- L’organisateur de réunion ou le délégué utilise Outlook pour planifier la réunion suivante en ajoutant l’URL de l’invitation à participer à la réunion. L’organisateur de réunion ou le délégué spécifie alors les utilisateurs à inviter et envoie les invitations à la réunion.
    
### <a name="specify-appropriate-scheduling-details"></a>Spécification des détails de planification appropriés

Une fois que l’équipe de support des grandes réunions qui traite la demande s’est assurée qu’aucune autre réunion n’est prévue à l’heure demandée, elle planifie la réunion dans le pool des grandes réunions. 
  
Pour garantir la meilleure expérience utilisateur, il est important de planifier la réunion de grande taille avec les niveaux de droit d’accès et les paramètres de réunion qui sont adaptés aux besoins de l’organisateur de la réunion. Prenez en compte les paramètres de planification suivants définis dans Skype pour les options de la réunion d’entreprise :
  
- Utilisez un nouvel espace de réunion pour chaque grande réunion au lieu de réutiliser l’espace de réunion dédié. 
    
- Spécifiez le niveau d’accès à la réunion, comme suit :
    
  - Si au moins un invité ne fait pas partie de l’organisation, optez pour le type d’accès à la réunion **Tout le monde (aucune restriction)**. Cela vous évitera ainsi d’avoir à gérer une grande salle d’attente pendant le déroulement de la réunion.
    
  - S’il s’agit d’une réunion interne, optez pour le type d’accès à la réunion **Toute personne de ma société**.
    
    > [!NOTE]
    > Évitez de choisir le type d’accès à la réunion **Personnes de mon entreprise que j’invite**, car lorsque vous utilisez ce paramètre, les organisateurs doivent ajouter toutes les adresses électroniques à la liste d’invités et vous ne pouvez pas inviter un groupe de distribution. Évitez de choisir le type d’accès à la réunion **Seulement moi, l’organisateur de la réunion**, car ce paramètre exige que chaque participant de la réunion, y compris les présentateurs, se trouve dans la salle d’attente à l’heure de la réunion. La personne responsable du déroulement de la grande réunion doit alors surveiller constamment la liste de la salle d’attente et admettre les nouveaux utilisateurs qui se trouvent dans la salle d’attente.
  
- Autorisez les utilisateurs qui se connectent à partir d’un téléphone à accéder automatiquement à la réunion en cochant le paramètre **Les appelants sont admis directement**.
    
- Invitez explicitement les utilisateurs suivants :
    
  - Organisateur de la réunion et délégué (demandeur)
    
  - Liste des présentateurs fournie par un demandeur de réunion
    
    > [!NOTE]
    > Si le type d’accès à la réunion défini est **Personnes que je choisis**, vous devez ajouter explicitement chaque participant à une grande réunion en tant qu’invité de la réunion. 
  
- Au lieu d’attribuer à l’option de présentateur l’une des valeurs de promotion automatique, gérez explicitement les présentateurs. Veillez à ajouter les utilisateurs ci-dessous en tant que présentateurs :
    
  - Organisateur de la réunion et délégué (demandeur)
    
  - Liste des présentateurs fournie par les demandeurs de grande réunion
    
    En gérant explicitement les présentateurs, vous limitez le nombre de présentateurs et favorisez ainsi le bon déroulement d’une grande réunion. Si la majorité des participants à la réunion possèdent un rôle de participant, cela limite le risque que des personnes prennent accidentellement le contrôle de la présentation, suppriment une présentation PowerPoint, désactivent ou activent le son pour les présentateurs et perturbent le déroulement de la réunion. 
    
- Cochez le paramètre **Désactiver le son pour tous les participants** afin que seuls les présentateurs puissent diffuser du son lors de la réunion.
    
- Vérifiez que le **bloc vidéo des participants** à vous assurer seulement les présentateurs peuvent de diffusion vidéo à la réunion.
    
### <a name="create-a-conferencing-policy"></a>Création d’une stratégie de conférence

Créez une stratégie de conférence spécifique aux grandes réunions, puis affectez cette stratégie aux utilisateurs hébergés dans le pool dédié aux grandes réunions. Configurez la stratégie de conférence avec les paramètres suivants :
  
- L’option **MaxMeetingSize** la valeur 1000. (La valeur par défaut est 250.)
    
- Définissez l’option **AllowLargeMeetings** sur **True**. 
    
- Définissez l’option **EnableAppDesktopSharing** sur **Aucun**.
    
- Définissez l’option **AllowUserToScheduleMeetingsWithAppSharing** sur **False**.
    
- Définissez l’option **AllowSharedNotes** sur **False**.
    
- Définissez l’option **AllowAnnotations** sur **False**.
    
- Définissez l’option **DisablePowerPointAnnotations** sur **True**.
    
- Définissez l’option **AllowMultiview** sur **False**.
    
- Définissez l’option **EnableMultiviewJoin** sur **False**.
    
> [!NOTE]
> Prise en charge des réunions de grande taille dans Skype pour Business Server requiert que le paramètre **AllowLargeMeetings** est défini sur true. Lorsque ce paramètre a la valeur true, le Skype pour une expérience sera optimisée pour les réunions de grande échelle lorsque les utilisateurs joindre à la réunion. En particulier, dans une grande réunion, Skype pour entreprise n’affichera pas l’initiale ou la mise à jour de la liste des participants totale de la réunion, qui est un goulot d’étranglement de performances pour le client et Skype pour Business Server. Au lieu de cela, Skype pour entreprise affiche uniquement des informations sur l’utilisateur et la liste des présentateurs de la réunion. Skype pour entreprise affiche toujours le nombre total de participants disponibles dans les réunions de grande taille.
  
À l’exception du paramètre **Taille maximale de la réunion**, tous les autres paramètres de stratégie de conférence spécifiés ici sont nécessaires pour désactiver les fonctions de conférence qui ne sont pas nécessaires pour les grandes réunions.
  
En outre, vous devez configurer le pool réunion dédié afin que chaque Skype pour utilisateur Business Server hébergées sur le pool et responsable de la gestion de la planification de la réunion dispose des autorisations appropriées. À cet effet, procédez ainsi :
  
- Définissez l’option **Désigné comme présentateur** sur **Aucun**. En général, parmi tous les participants, un ou plusieurs utilisateurs sont des présentateurs. Les participants ne doivent pas être admis automatiquement dans des grandes réunions en tant que présentateurs. Les présentateurs doivent être désignés explicitement lors de la planification de la réunion ou promus explicitement lors de la réunion.
    
- Assurez-vous que la case à cocher **Type de conférence affecté par défaut** n’est pas activée. Ce paramètre contrôle si le complément de réunion en ligne pour Skype pour entreprise toujours planifie les conférences à l’aide de l’organisateur affecté de conférence, qui signifie que des réunions programmées ont la même URL de jointure et les informations audio. Dans des scénarios de collaboration en petit groupe, l’utilisation de ce type de conférence est pratique, car une conférence individuelle est affectée à chacun, et l’URL pour participer, ainsi que les informations audio constantes, permettant de rejoindre facilement la réunion. En revanche, dans des scénarios de grande réunion, l’équipe de support planifie les grandes réunions avec un ensemble d’informations d’identification d’utilisateur et fournit les URL et les informations audio aux demandeurs de la réunion. Dans ce cas, l’utilisation d’une URL différente pour rejoindre chaque réunion est préférable.
    
- Vérifiez que la case à cocher **Admettre les utilisateurs anonymes par défaut** n’est pas activée, sauf si elle est nécessaire. Ce paramètre affecte la valeur par défaut de type accès prévue par le complément de réunion en ligne Skype pour l’entreprise lorsque vous n’utilisez ne pas une conférence affectée de la conférence. L’option appropriée pour ce paramètre dépend des besoins de votre organisation. Si les grandes réunions de votre organisation sont des réunions internes, ne sélectionnez pas cette option. Si la plupart des grandes réunions nécessitent la participation d’utilisateurs externes, sélectionnez cette option.
    
Pour plus d’informations sur la création d’une stratégie de conférences, voir [Gérer les stratégies de conférence dans Skype pour Business Server 2015](../../manage/conferencing/conferencing-policies.md).
  

