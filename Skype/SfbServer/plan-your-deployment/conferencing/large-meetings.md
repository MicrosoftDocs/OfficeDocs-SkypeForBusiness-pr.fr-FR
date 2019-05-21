---
title: Planifier des réunions de grande envergure dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Résumé: cette rubrique vous présente les meilleures pratiques en matière de mise en œuvre et de gestion de grandes réunions dans Skype entreprise Server.'
ms.openlocfilehash: 0ed044a811d4a482690be13c8626f93089aa24a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277320"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planifier des réunions de grande envergure dans Skype entreprise Server
 
**Résumé:** Consultez cette rubrique pour en savoir plus sur les meilleures pratiques en matière d’implémentation et de gestion de grandes réunions dans Skype entreprise Server.
  
La taille des réunions prises en charge par Skype entreprise Server varie selon que les conférences sont hébergées sur un pool partagé ou dédié: n’importe où dans les participants 250 d’un pool partagé à 1000 participants sur un pool dédié. 
  
> [!NOTE]
> Cette rubrique décrit les meilleures pratiques en matière de réunions importantes prises en charge par Skype entreprise Server. Si votre organisation nécessite des capacités de réunion plus importantes, vous devez envisager de mettre en place un environnement hybride qui tire parti de la diffusion de réunion Skype, un nouveau service en ligne intégré à Office 365. 

> [!NOTE]
> La diffusion de réunion Skype permet aux utilisateurs d’héberger et de diffuser des réunions à des réunions en ligne comptant jusqu’à 10 000 participants. L’utilisation de la diffusion de réunion Skype exige que Skype Entreprise Server soit déjà configuré dans une configuration hybride avec un client Office 365 de production. Un client en ligne doit être installé au préalable pour tous les utilisateurs. Si vous êtes intéressé par le déploiement d’une solution hybride qui peut tirer parti de la diffusion de réunion Skype, reportez-vous à [la rubrique qu’est-ce qu’une diffusion de réunion Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) et configurez [votre déploiement local pour la diffusion de réunion Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Les grandes réunions possèdent généralement les caractéristiques suivantes :
  
- Le format de la réunion est celui d’une présentation un-à-plusieurs.
    
- Un ou plusieurs utilisateurs sont des présentateurs. Le reste de l’assistance sont des participants.
    
- Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.
    
- L’audio est nécessaire et la vidéo peut également être utilisée.
    
- Une personne dédiée, généralement l’organisateur de la réunion ou un assistant de l’organisateur, prépare la réunion à l’avance.
    
- Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, de façon appropriée.
    
Lorsqu’un utilisateur planifie une réunion, Skype entreprise Server crée un enregistrement dans la base de données de conférence, qui stocke les données de conférence, mais ne réserve aucune ressource matérielle pour la réunion planifiée à l’avance. Au lieu de cela, Skype entreprise Server dispose d’une logique d’équilibrage de charge intégrée pour allouer dynamiquement les ressources de conférence sur les serveurs frontaux de telle sorte que la distribution de charge de manière égale sur tous les serveurs frontaux de la liste. Cela permet de mettre en service et d’utiliser des ressources matérielles, mais il est important de prévoir correctement la prise en charge des réunions de très grande taille. 
  
Par exemple, quand une grappe de serveurs Skype entreprise est en cours d’exécution en temps réel, chaque serveur frontal peut héberger approximativement 125 réunions de taille moyenne. L’ajout d’une autre réunion de petite taille ne serait pas un obstacle à la différence d’une réunion de 1 000 utilisateurs, car les serveurs frontaux ne pourraient probablement pas prendre en charge une grande réunion en même temps que les 125 autres réunions.
  
La prise en charge de réunions de grande taille (1 000 participants) nécessite de régler les aspects liés à la fois au modèle matériel partagé et au modèle d’absence de réservation. En règle générale, vous devez planifier une réserve dédiée et suivre les pratiques recommandées comme décrit dans les sections suivantes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planification d’un pool dédié

Si votre organisation a besoin de réunions de plus de 250 participants, vous devez planifier un pool dédié pour prendre en charge cette capacité. 
  
Pour disposer de suffisamment de ressources aux niveaux du processeur et de la mémoire pour les réunions incluant jusqu’à 1 000 utilisateurs, les serveurs frontaux d’hébergement ne doivent pas gérer de fonctionnalités de messagerie instantanée et de présence, ni de charges de travail liées à Voix Entreprise. Ils ne doivent pas non plus héberger d’autres réunions, quelles que soient leurs tailles. Pour animer des réunions de plus de 1000 utilisateurs, vous devez configurer un pool Skype entreprise Server distinct destiné à accueillir des réunions de grande envergure.
  
Dans le cas d’un pool de serveurs Skype entreprise destiné à accueillir des réunions de grande taille, il est préférable d’héberger une seule réunion d’au maximum 1000 utilisateurs, de telle sorte que les heures de réunion doivent être réservées à l’avance via un processus de planification hors-bande pour garantir une prise en charge dédiée du Serveurs frontaux. Pour prendre en charge plusieurs réunions de grande taille en même temps, vous devez configurer plusieurs pools de réunions volumineux dédiées.
  
Pour plus d’informations sur la configuration matérielle et logicielle requise et sur la planification d’une topologie qui prend en charge les réunions de grande taille, voir [Configuration matérielle et logicielle requise pour les conférences dans Skype entreprise Server](hardware-and-software-requirements.md) et [planification de votre topologie de conférence pour Skype entreprise Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Mise en œuvre des meilleures pratiques pour les grandes réunions

Après avoir configuré un pool dédié pour les grandes réunions, vous pouvez suivre une procédure permettant de garantir que les grandes réunions hébergées dans le pool offrent une expérience utilisateur optimale. Les rubriques de cette section donnent des informations sur la gestion de grandes réunions :
  
- Création d’organisateurs de réunion dédiés
    
- Création de modérateurs dédiés
    
- Gestion d’un calendrier distinct des grandes réunions
    
- Mise en œuvre d’une procédure/// de planification des grandes réunions
    
- Spécification des détails de planification appropriés
    
- Création d’une stratégie de conférence pour les grandes réunions
    
### <a name="create-dedicated-meeting-organizers"></a>Création d’organisateurs de réunion dédiés

Pour réduire le trafic de communications en temps réel dans le grand pool de réunions, Microsoft ne recommande pas aux utilisateurs qui se connectent régulièrement à l’aide de clients Skype entreprise et qui participent à la messagerie instantanée, à la présence, aux conférences et aux sessions vocales. Il est préférable de suivre les étapes suivantes :
  
- Création d’un ou de plusieurs comptes d’utilisateur dédiés à la planification des grandes réunions
    
- Hébergement des comptes d’utilisateur du personnel responsable de la planification des grandes réunions dans un pool de grandes réunions
    
### <a name="create-dedicated-moderators"></a>Création de modérateurs dédiés

Les réunions pouvant inclure de plusieurs centaines à un millier d’utilisateurs, il est recommandé de désigner une personne dédiée chargée d’animer la session en ligne d’une grande réunion. Cette personne dédiée peut être déléguée de l’organisateur de la réunion ou d’un membre du personnel d’assistance technique de l’organisation. Il est important d’ajouter le modérateur de réunion dédié comme présentateur au moment où la réunion est programmée, même s’il soit possible de promouvoir un participant de la réunion en ligne au rôle de présentateur pendant la réunion.
  
Le modérateur de la réunion peut utiliser toutes les fonctionnalités du présentateur des clients Skype entreprise pour gérer la grande réunion. Ces fonctionnalités sont les suivantes :
  
- Surveillance de la salle d’attente et l’admission ou le rejet des utilisateurs dans la salle d’attente
    
- Suppression des utilisateurs qui ne doivent pas participer à la réunion
    
- Modification des types d’accès à la réunion
    
- Modification des rôles des participants
    
- Inviter des participants supplémentaires lors de la réunion par glisser-déplacer, par numéro de téléphone ou par courrier électronique
    
- Activation et désactivation du micro du public ou des utilisateurs individuels
    
- Gestion du contenu de réunion, dont le téléchargement de contenu, la suppression du contenu et le basculement du contenu actif

    
### <a name="maintain-a-separate-calendar"></a>Gestion d’un calendrier distinct

Pour chaque pool de réunions de grande taille, vous devriez gérer un calendrier distinct des réunions de grande taille planifiées dans le pool. Par exemple, vous pouvez utiliser un seul compte d’utilisateur dans le grand groupe de réunions et utiliser Outlook avec Exchange et le complément réunion en ligne pour Skype entreprise pour gérer un calendrier différent. Si vous utilisez plusieurs comptes d’utilisateurs pour permettre au support technique de créer des réunions de grande taille, vous pouvez configurer un calendrier distinct qui regroupe toutes les réunions de grande taille créées par les membres du personnel de support technique. 
  
La gestion d’un calendrier distinct des réunions de grande taille contribue à éviter les conflits et permet de s’assurer que seule une réunion de grande taille est active à un moment donné.
  
### <a name="implement-a-scheduling-process"></a>Mise en œuvre d’une procédure de planification

Étant donné qu’une seule grande réunion à la fois est prise en charge sur le pool de réunions important, vous devez implémenter un processus de planification de grande réunion pour faciliter la configuration des réunions de grande envergure et éviter les conflits. Cette fonctionnalité n’est pas fournie directement par Skype entreprise Server ou par le biais d’un client Skype entreprise. Un moyen d’implémenter ce processus consiste à utiliser le système de tickets de l’équipe de support de votre organisation, le cas échéant.
  
La planification d’une grande réunion implique de suivre la procédure suivante :
  
- Outre la liste de présentateurs, l’organisateur de réunion ou le délégué détermine l’heure, la durée et la taille d’une prochaine réunion. Si la taille de réunion prévue dépasse 250 utilisateurs ou pour garantir la meilleure expérience pour une réunion de moins de 250 utilisateurs, l’organisateur ou le délégué envoie une demande pour une grande réunion.
    
- Le personnel chargé de la planification vérifie si la date et l’heure demandées sont disponibles. Comme nous ne prenons en charge qu’une seule grande réunion à la fois sur le pool dédié, le personnel de planification doit vérifier le calendrier des grandes réunions pour déterminer si une autre réunion est planifiée à la date et à l’heure demandées. Si l’heure demandée est disponible, le personnel approuve la demande de réunion.
    
- S’il s’agit d’une demande approuvée, le personnel de planification (à l’aide des informations d’identification de la réserve dédiée) utilise le complément réunion en ligne pour Skype entreprise avec Outlook pour organiser une réunion sur le pool de réunions volumineux dédié. L’URL à utiliser pour participer à la réunion est fournie par le demandeur dans le cadre de l’avis d’approbation.
    
- L’organisateur de réunion ou le délégué utilise Outlook pour planifier la réunion suivante en ajoutant l’URL de l’invitation à participer à la réunion. L’organisateur de réunion ou le délégué spécifie alors les utilisateurs à inviter et envoie les invitations à la réunion.
    
### <a name="specify-appropriate-scheduling-details"></a>Spécification des détails de planification appropriés

Une fois que l’équipe de support des grandes réunions qui traite la demande s’est assurée qu’aucune autre réunion n’est prévue à l’heure demandée, elle planifie la réunion dans le pool des grandes réunions. 
  
Pour garantir une meilleure utilisation de l’utilisateur, il est important de planifier la grande réunion avec les niveaux d’accès et les paramètres de réunion adaptés aux besoins de l’organisateur de la réunion. Prenez en compte les paramètres de planification suivants configurés dans les options de réunion de Skype entreprise:
  
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
    
- Cochez la case **bloquer la vidéo des participants** pour vous assurer que seuls les présentateurs peuvent diffuser la vidéo dans la réunion.
    
### <a name="create-a-conferencing-policy"></a>Création d’une stratégie de conférence

Créez une stratégie de conférence spécifique aux grandes réunions, puis affectez cette stratégie aux utilisateurs hébergés dans le pool dédié aux grandes réunions. Configurez la stratégie de conférence avec les paramètres suivants :
  
- Définissez l’option **MaxMeetingSize** sur 1000. (La valeur par défaut est 250.)
    
- Définissez l’option **AllowLargeMeetings** sur **True**. 
    
- Définissez l’option **EnableAppDesktopSharing** sur **Aucun**.
    
- Définissez l’option **AllowUserToScheduleMeetingsWithAppSharing** sur **False**.
    
- Définissez l’option **AllowSharedNotes** sur **False**.
    
- Définissez l’option **AllowAnnotations** sur **False**.
    
- Définissez l’option **DisablePowerPointAnnotations** sur **True**.
    
- Définissez l’option **AllowMultiview** sur **False**.
    
- Définissez l’option **EnableMultiviewJoin** sur **False**.
    
> [!NOTE]
> La prise en charge des réunions de grande envergure dans Skype entreprise Server nécessite la définition du paramètre **AllowLargeMeetings** sur true. Lorsque ce paramètre est défini sur true, l’expérience Skype entreprise est optimisée pour les réunions en plus grande envergure lorsque les utilisateurs rejoignent la réunion. En particulier, dans une grande réunion, Skype entreprise ne verra pas la première ou la mise à jour de la liste des participants à la réunion complète, qui est un goulet d’étranglement du client et de Skype entreprise Server. Skype entreprise n’affiche que les informations relatives à l’utilisateur et à la liste des présentateurs de la réunion. Skype entreprise affiche le nombre total de participants au cours des réunions de grande envergure.

Le paramètre-AllowLargeMeetings $true entraîne ce qui suit: · Masque la liste des participants. · Désactive les erreurs dans la fenêtre de messagerie instantanée.
· Désactive la vidéo à plusieurs.
· Désactive la possibilité de promouvoir un participant au présentateur. Vous devez planifier avant et déclarer tous les présentateurs avant la réunion.
· Désactive la possibilité d’activer le son pour les participants individuels.
· Désactive la possibilité d’appliquer la fonctionnalité verrouiller les actualités vidéo aux participants.
· La fonction d’appel RTC n’est pas en mesure d’activer le son avec * 6, car l’assistance virtuelle individuelle qui est responsable des commandes DTMF dans les réunions actives de grande envergure est manquante.
· Si le présentateur ou l’organisateur planifie une réunion où tout le monde doit être coupé en premier («muet tout»), les utilisateurs PSTN seront désactivés pendant l’appel et ne seront pas en mesure d’activer le son.

À l’exception du paramètre **Taille maximale de la réunion**, tous les autres paramètres de stratégie de conférence spécifiés ici sont nécessaires pour désactiver les fonctions de conférence qui ne sont pas nécessaires pour les grandes réunions.
  
Par ailleurs, vous devez configurer le pool de réunions volumineux dédié de sorte que chaque utilisateur de Skype entreprise Server hébergé sur le pool et responsable de la gestion de la planification de la réunion dispose des autorisations appropriées. À cet effet, procédez ainsi :
  
- Définissez l’option **Désigné comme présentateur** sur **Aucun**. En général, parmi tous les participants, un ou plusieurs utilisateurs sont des présentateurs. Les participants ne doivent pas être admis automatiquement dans des grandes réunions en tant que présentateurs. Les présentateurs doivent être désignés explicitement lors de la planification de la réunion ou promus explicitement lors de la réunion.
    
- Assurez-vous que la case à cocher **Type de conférence affecté par défaut** n’est pas activée. Ce paramètre détermine si le complément réunion en ligne pour Skype entreprise planifie toujours des conférences à l’aide de la Conférence affectée à l’organisateur, ce qui signifie que les réunions planifiées ont les mêmes URL et informations audio. Dans des scénarios de collaboration en petit groupe, l’utilisation de ce type de conférence est pratique, car une conférence individuelle est affectée à chacun, et l’URL pour participer, ainsi que les informations audio constantes, permettant de rejoindre facilement la réunion. En revanche, dans des scénarios de grande réunion, l’équipe de support planifie les grandes réunions avec un ensemble d’informations d’identification d’utilisateur et fournit les URL et les informations audio aux demandeurs de la réunion. Dans ce cas, l’utilisation d’une URL différente pour rejoindre chaque réunion est préférable.
    
- Vérifiez que la case à cocher **Admettre les utilisateurs anonymes par défaut** n’est pas activée, sauf si elle est nécessaire. Ce paramètre affecte le type d’accès par défaut aux réunions planifié par le complément réunion en ligne pour Skype entreprise sans utiliser de conférence. L’option appropriée pour ce paramètre dépend des besoins de votre organisation. Si les grandes réunions de votre organisation sont des réunions internes, ne sélectionnez pas cette option. Si la plupart des grandes réunions nécessitent la participation d’utilisateurs externes, sélectionnez cette option.
    
Pour plus d’informations sur la création d’une stratégie de conférence, voir [gérer les stratégies de conférence dans Skype entreprise Server](../../manage/conferencing/conferencing-policies.md).
  

