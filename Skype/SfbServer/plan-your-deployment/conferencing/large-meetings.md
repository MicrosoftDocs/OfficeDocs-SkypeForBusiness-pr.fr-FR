---
title: Planifier des réunions de grande taille dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les meilleures pratiques en matière d’implémentation et de gestion des grandes réunions Skype Entreprise Server.'
ms.openlocfilehash: a9ab532914a69f70cea6d54fb7935a7d8a44c98d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856541"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planifier des réunions de grande taille dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les meilleures pratiques en matière d’implémentation et de gestion de grandes réunions Skype Entreprise Server.
  
La taille des réunions que Skype Entreprise Server peut prendre en charge varie selon que la conférence est hébergée sur un pool partagé ou dédié : entre 250 participants sur un pool partagé et 1 000 participants sur un pool dédié. 
  
> [!NOTE]
> Cette rubrique se concentre sur les meilleures pratiques pour les grandes réunions pris en charge par les Skype Entreprise Server. Si votre organisation nécessite des fonctionnalités de réunion plus importantes, vous devez envisager d’implémenter un environnement hybride qui tire parti de Réunion Skype Broadcast, un nouveau service en ligne qui fait partie de Microsoft 365 et Office 365. 

> [!NOTE]
> Réunion Skype La diffusion permet aux utilisateurs d’héberger et de diffuser des réunions à un large public en ligne de 10 000 participants au plus. L’utilisation de Réunion Skype diffusion nécessite que Skype Entreprise Server soit déjà configuré dans une configuration hybride avec une organisation Microsoft 365 ou Office 365 production. Tous les utilisateurs doivent avoir un client en ligne établi en tant que prérequis. Si vous souhaitez déployer une solution hybride qui peut tirer parti de la diffusion Réunion Skype, consultez Qu’est-ce qu’une diffusion [Réunion Skype ?](https://go.microsoft.com/fwlink/?LinkId=617071) et configurez votre déploiement local pour la diffusion [Réunion Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Les grandes réunions ont généralement les caractéristiques suivantes :
  
- Le format de la réunion est celui d’une présentation un-à-plusieurs.
    
- Un ou plusieurs utilisateurs constituent les présentateurs. Le reste de l’assistance constitue les participants.
    
- Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.
    
- L’audio est nécessaire et la vidéo peut également être utilisée.
    
- Une personne dédiée, généralement l’organisateur de la réunion ou un assistant de l’organisateur, définit la réunion bien à l’avance.
    
- Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, le cas échéant.
    
Lorsqu’un utilisateur planifiera une réunion, Skype Entreprise Server crée un enregistrement dans la base de données de conférence, qui stocke les données de conférence, mais ne réserve aucune ressource matérielle pour la réunion prévue à l’avance. Au lieu de cela, Skype Entreprise Server dispose d’une logique d’équilibrage de charge intégrée pour allouer dynamiquement des ressources de conférence sur les serveurs frontaux de manière à répartir les charges de manière égale sur tous les serveurs frontaux du pool. Cela permet de mettre en place et d’utiliser efficacement des ressources matérielles, mais il est important de planifier correctement la prise en charge de très grandes réunions. 
  
Par exemple, lorsqu’un pool Skype Entreprise Server est proche de sa capacité maximale, chaque serveur frontal peut héberger environ 125 réunions de taille moyenne. L’ajout d’une autre petite réunion ne serait pas un problème, mais l’ajout d’une réunion à 1 000 utilisateurs serait un problème, car les serveurs frontaux ne pourraient probablement pas prendre en charge une réunion aussi importante en même temps que les 125 autres réunions.
  
La prise en charge de grandes réunions de 1 000 participants au plus nécessite de résoudre les problèmes liés au modèle matériel partagé et au modèle sans réservation. En règle générale, vous devez planifier un pool dédié et suivre les meilleures pratiques décrites dans les sections suivantes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planifier un pool dédié

Si votre organisation nécessite des réunions de plus de 250 participants, vous devez planifier un pool dédié pour prendre en charge la charge. 
  
Pour avoir suffisamment de ressources de processeur et de mémoire pour les réunions de 1 000 utilisateurs au plus, les serveurs frontaux d’hébergement ne doivent pas héberger d’autres charges de travail de messagerie instantanée et de présence ou de Voix Entreprise messagerie instantanée. Les serveurs ne doivent pas non plus héberger d’autres réunions, quelle que soit la taille des autres réunions. Pour héberger des réunions de 1 000 utilisateurs au plus, vous devez configurer un pool Skype Entreprise Server distinct dédié à l’hébergement de grandes réunions.
  
Un pool Skype Entreprise Server dédié à l’hébergement de grandes réunions doit héberger une seule réunion de 1 000 utilisateurs au plus en même temps, de sorte que les heures de réunion doivent être réservées à l’avance via un processus de planification hors bande pour garantir une prise en charge dédiée des serveurs frontaux. Pour prendre en charge plusieurs grandes réunions en même temps, vous devez configurer plusieurs pools dédiés aux grandes réunions.
  
Pour plus d’informations sur la configuration matérielle et logicielle requise et la planification d’une topologie qui prend en charge les grandes réunions, voir Configuration matérielle et logicielle requise pour les conférences dans [Skype Entreprise Server](hardware-and-software-requirements.md) et Planifier votre topologie de conférence pour [Skype Entreprise Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implémenter les meilleures pratiques pour les grandes réunions

Après avoir mis en place un pool dédié pour les grandes réunions, vous pouvez prendre des mesures pour vous assurer que les grandes réunions hébergées dans le pool offrent la meilleure expérience utilisateur. Les sections suivantes fournissent des instructions pour la gestion des grandes réunions :
  
- Créer des organisateurs de réunion dédiés
    
- Créer des modérateurs dédiés
    
- Gérer un calendrier distinct de grandes réunions
    
- Implémenter un processus de planification de grandes réunions
    
- Spécifier les détails de planification appropriés
    
- Créer une stratégie de conférence pour les grandes réunions
    
### <a name="create-dedicated-meeting-organizers"></a>Créer des organisateurs de réunion dédiés

Pour réduire le trafic des communications en temps réel dans le pool de grandes réunions, Microsoft ne recommande pas l’hébergement d’utilisateurs qui se connectent régulièrement à l’aide de clients Skype Entreprise et participent à des sessions de messagerie instantanée, de présence, de conférence et de voix. À la place, faites l’une des choses suivantes :
  
- Créer un ou plusieurs comptes d’utilisateur dédiés uniquement pour la planification de grandes réunions
    
- Accueil des comptes d’utilisateur du personnel responsable de la planification de grandes réunions sur un pool de grandes réunions
    
### <a name="create-dedicated-moderators"></a>Créer des modérateurs dédiés

Avec plusieurs centaines à un millier d’utilisateurs dans une réunion, il est bon d’avoir une personne dédiée qui modère la session en ligne d’une grande réunion. Cette personne dédiée peut être déléguée de l’organisateur de la réunion ou membre du personnel de support technique des grandes réunions de l’organisation. Il est important d’ajouter le modérateur de réunion dédié comme présentateur au moment où la réunion est programmée, même s’il soit possible de promouvoir un participant de la réunion en ligne au rôle de présentateur pendant la réunion.
  
Le modérateur de réunion peut utiliser toutes les fonctionnalités de présentateur Skype Entreprise clients pour gérer la grande réunion. Ces fonctionnalités sont les suivantes :
  
- Surveillance de la salle d’accueil et admission ou rejet des utilisateurs dans la salle d’accueil
    
- Suppression de tous les utilisateurs de la réunion qui ne doivent pas y être
    
- Modification des types d’accès aux réunions
    
- Modification des rôles des participants
    
- Invitation de participants supplémentaires pendant la réunion à l’aide de la fonctionnalité glisser-déposer, de numérotation téléphonique ou d’e-mail
    
- Activer et désactiver le son de l’audience ou des utilisateurs individuels
    
- Gestion du contenu de réunion, y compris le téléchargement de contenu, la suppression de contenu et le changement de contenu actif

    
### <a name="maintain-a-separate-calendar"></a>Gérer un calendrier distinct

Pour chaque pool de grandes réunions, vous devez conserver un calendrier distinct de grandes réunions prévues sur ce pool. Par exemple, vous pouvez home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype Entreprise to maintain a separate calendar. Si vous utilisez plusieurs comptes d’utilisateurs pour permettre au personnel de support technique de créer des réunions de grande taille, vous pouvez configurer un calendrier distinct qui regroupe toutes les réunions de grande taille créées par les membres du personnel de support technique. 
  
La gestion d’un calendrier distinct des réunions de grande taille contribue à éviter les conflits et permet de s’assurer que seule une réunion de grande taille est active à un moment donné.
  
### <a name="implement-a-scheduling-process"></a>Implémenter un processus de planification

Étant donné qu’une seule grande réunion à la fois est prise en charge sur le pool dédié aux grandes réunions, vous devez implémenter un processus de planification de grandes réunions pour faciliter la configuration de grandes réunions et éviter les conflits. Cette fonctionnalité n’est pas fournie directement par Skype Entreprise Server ou Skype Entreprise clients. L’une des façons d’implémenter un tel processus consiste à utiliser le système de tickets de l’équipe de support de votre organisation, si disponible.
  
La planification d’une grande réunion implique d’effectuer les étapes suivantes :
  
- L’organisateur de réunion ou le délégué détermine l’heure, la durée et la taille d’une prochaine réunion, en plus de la liste de présentateurs. Si la taille de réunion anticipée dépasse 250 utilisateurs ou pour garantir la meilleure expérience pour une réunion de moins de 250 utilisateurs, l’organisateur ou le délégué soumet une demande pour une grande réunion.
    
- Le personnel en charge de la planification vérifie si la date et l’heure demandées sont disponibles. Comme nous ne prenons en charge qu’une seule grande réunion à la fois sur le pool dédié, le personnel de planification doit vérifier le calendrier de grandes réunions pour déterminer si une autre réunion est planifiée pour la date et l’heure demandées. Si l’heure demandée est disponible, le personnel approuve la demande de réunion.
    
- Si la demande est approuvée, le personnel de planification (à l’aide des informations d’identification sur le pool dédié) utilise le add-in de réunion en ligne pour Skype Entreprise avec Outlook pour configurer une réunion sur le pool dédié aux grandes réunions. L’URL à utiliser pour participer à la réunion est fournie par le demandeur dans le cadre de l’avis d’approbation.
    
- L’organisateur de réunion ou le délégué utilise Outlook pour planifier la réunion à venir, en ajoutant l’URL de la réunion à l’invitation à la réunion. L’organisateur de réunion ou le délégué spécifie alors les utilisateurs à inviter et envoie les invitations à la réunion.
    
### <a name="specify-appropriate-scheduling-details"></a>Spécifier les détails de planification appropriés

Après s’être assurée qu’aucune autre réunion n’est prévue à l’heure demandée, l’équipe de support des grandes réunions qui traite la demande planifie la réunion dans le pool de grandes réunions. 
  
Pour garantir la meilleure expérience utilisateur possible, il est important de planifier une grande réunion avec les niveaux d’accès appropriés et les paramètres de réunion adaptés aux besoins de l’organisateur de la réunion. Prenez en compte les paramètres de planification suivants configurés dans Skype Entreprise options de réunion :
  
- Utilisez un nouvel espace de réunion pour chaque grande réunion au lieu de réutiliser l’espace de réunion dédié. 
    
- Spécifiez le niveau d’accès à la réunion comme suit :
    
  - Si au moins un invité est externe à l’organisation, définissez le type d’accès à la réunion sur Tout le monde **(aucune restriction).** Cela vous évitera ainsi d’avoir à gérer une grande salle d’attente pendant le déroulement de la réunion.
    
  - S’il s’agit d’une réunion interne, optez pour le type d’accès à la réunion **Toute personne de ma société**.
    
    > [!NOTE]
    > Évitez de choisir le type d’accès à la réunion **Personnes de ma société invitées**. En effet, ce paramètre contraint les organisateurs à ajouter toutes les adresses de messagerie des utilisateurs à la liste d’invités et il vous empêche d’inviter un groupe de distribution. Évitez de choisir le type d’accès à la réunion **Seulement moi, l’organisateur de la réunion**, car ce paramètre exige que chaque participant à la réunion, y compris les présentateurs, se trouve dans la salle d’attente à l’heure d’exécution de la réunion. La personne responsable de l’exécution de la grande réunion doit alors constamment surveiller la liste de la salle d’attente et admettre les nouveaux utilisateurs qui se trouvent dans la salle d’attente.
  
- Autorisez les utilisateurs qui se connectent à partir d’un téléphone à accéder automatiquement à la réunion en cochant le paramètre **Les appelants sont admis directement**.
    
- Invitez explicitement les utilisateurs suivants :
    
  - organisateur de la réunion et délégué (demandeur) ;
    
  - liste des présentateurs fournie par un demandeur de réunion.
    
    > [!NOTE]
    > Si le type d’accès à la réunion défini est **Personnes que je choisis**, vous devez ajouter explicitement chaque participant à une grande réunion en tant qu’invité de la réunion. 
  
- Au lieu d’attribuer à l’option de présentateur l’une des valeurs de promotion automatique, gérez explicitement les présentateurs. Veillez à ajouter les utilisateurs suivants en tant que présentateurs :
    
  - organisateur de la réunion et délégué (demandeur) ;
    
  - liste des présentateurs fournie par les demandeurs de grande réunion.
    
    En gérant explicitement les présentateurs, vous pouvez limiter le nombre de présentateurs à un nombre suffisant pour qu’il soit possible d’avoir une grande réunion efficace. Si la majorité des participants à la réunion ont un rôle de participant, cela limite les chances de voir des personnes prendre accidentellement le contrôle de la présentation, supprimer une présentation PowerPoint, désactiver ou activer le son pour les présentateurs et perturber le déroulement de la réunion. 
    
- Cochez le paramètre **Désactiver le son pour tous les participants** pour faire en sorte que seuls les présentateurs puissent diffuser du son au cours de la réunion.
    
- Vérifiez le **paramètre vidéo Bloquer les participants** pour vous assurer que seuls les présentateurs peuvent diffuser des vidéos dans la réunion.
    
### <a name="create-a-conferencing-policy"></a>Créer une stratégie de conférence

Créez une stratégie de conférence spécifique aux grandes réunions, puis affectez la stratégie de conférence aux utilisateurs qui sont sur le pool dédié aux grandes réunions. Configurez la stratégie de conférence avec les paramètres suivants :
  
- Définissez **l’option MaxMeetingSize** sur 1000. (La valeur par défaut est 250.)
    
- Définissez l’option **AllowLargeMeetings** à **True**. 
    
- Définissez l’option **EnableAppDesktopSharing** à **Aucun**.
    
- Définissez l’option **AllowUserToScheduleMeetingsWithAppSharing** à **False**.
    
- Définissez l’option **AllowSharedNotes** à **False**.
    
- Définissez l’option **AllowAnnotations** à **False**.
    
- Définissez l’option **DisablePowerPointAnnotations** à **True**.
    
- Définissez l’option **AllowMultiview** à **False**.
    
- Définissez l’option **EnableMultiviewJoin** à **False**.
    
> [!NOTE]
> La prise en charge des grandes réunions Skype Entreprise Server nécessite que le paramètre **AllowLargeMeetings** soit définie sur true. Lorsque ce paramètre est vrai, l’expérience Skype Entreprise est optimisée pour les réunions très importantes lorsque les utilisateurs rejoignent la réunion. Plus précisément, dans une grande réunion, Skype Entreprise n’affichera pas la liste initiale ou la mise à jour de la liste complète des participants à la réunion, ce qui constitue un goulot d’étranglement des performances pour le client et les Skype Entreprise Server. Au lieu de cela, Skype Entreprise affichera uniquement les informations sur l’utilisateur et la liste des présentateurs de la réunion. Skype Entreprise affiche toujours le nombre total de participants disponibles dans les grandes réunions.

Le **paramètre de $true AllowLargeMeetings** provoque les problèmes suivants :

- Masque la liste des participants. 

- Désactive les erreurs dans la fenêtre de messagerie instantanée.

- Désactive la vidéo multi-partie.

- Désactive la possibilité de promouvoir un participant au présentateur. Vous devez planifier à l’avance et déclarer tous les présentateurs avant la réunion.

- Désactive la possibilité de désactiver le son des participants individuels.

- Désactive la possibilité d’appliquer la fonctionnalité Verrouiller la vidéo à la une aux participants.

- Les utilisateurs de la numérotation PSTN ne pourront pas se réactiver à l’aide du numéro 6, car l’Assistance virtuelle personnelle responsable des commandes DTMF dans les grandes réunions actives est manquante.

- Si le présentateur/l’organisateur programme une réunion dans laquelle tout le monde doit être d’abord muté (« Désactiver tout ») les utilisateurs PSTN seront mutés tout au long de l’appel et ne pourront pas se réactiver eux-mêmes.

À l’exception du paramètre **Taille maximale de la réunion**, tous les autres paramètres de stratégie de conférence spécifiés ici sont requis afin de désactiver les fonctionnalités de conférence qui ne sont pas nécessaires pour les grandes réunions.
  
En outre, vous devez configurer le pool dédié aux grandes réunions afin que chaque utilisateur Skype Entreprise Server qui est sur le pool et responsable de la gestion de la planification des réunions dispose des autorisations appropriées. Pour ce faire, procédez ainsi :
  
- Définissez l’option **Désigné comme présentateur** à **Aucun**. En règle générale, un ou quelques utilisateurs parmi tous les participants sont des présentateurs, et les participants ne doivent pas être automatiquement admis dans des grandes réunions en tant que présentateurs. Les présentateurs doivent être explicitement désignés au moment de la planification de la réunion ou promus explicitement au cours de la réunion.
    
- Assurez-vous que la case à cocher **Type de conférence affecté par défaut** n’est pas sélectionnée. Ce paramètre contrôle si le add-in de réunion en ligne pour Skype Entreprise planifiera toujours des conférences à l’aide de la conférence attribuée par l’organisateur, ce qui signifie que les réunions programmées ont la même URL de rejoindre et les mêmes informations audio. Dans des scénarios de collaboration de petit groupe, l’utilisation de ce type de conférence est pratique, car tout le monde a sa conférence assignée individuelle et l’URL pour participer ainsi que les informations audio constantes permettent de rejoindre facilement la réunion. Cependant, dans des scénarios de grande réunion, l’équipe de support planifie les grandes réunions avec un ensemble d’informations d’identification d’utilisateur et fournit les URL et les informations audio aux demandeurs de la réunion. Dans ce cas, l’utilisation d’une URL différente pour rejoindre chaque réunion est préférable.
    
- Vérifiez que la case à cocher **Admettre les utilisateurs anonymes par défaut** n’est pas sélectionnée, sauf si elle est nécessaire. Ce paramètre affecte le type d’accès à la réunion par défaut prévu par le Skype Entreprise réunion en ligne lorsque vous n’utilisez pas de conférence affectée. L’option appropriée pour ce paramètre dépend des besoins de votre organisation. Si les grandes réunions de votre organisation sont des réunions internes, ne sélectionnez pas cette option. Si la plupart des grandes réunions nécessitent la participation d’utilisateurs externes, sélectionnez cette option.
    
Pour plus d’informations sur la création d’une stratégie de conférence, voir Gérer les stratégies de conférence [dans Skype Entreprise Server](../../manage/conferencing/conferencing-policies.md).
  

