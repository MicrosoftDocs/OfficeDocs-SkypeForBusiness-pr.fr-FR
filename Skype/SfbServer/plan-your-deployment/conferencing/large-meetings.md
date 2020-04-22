---
title: Planifier des réunions de grande taille dans Skype entreprise Server
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
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les meilleures pratiques pour la mise en œuvre et la gestion de grandes réunions dans Skype entreprise Server.'
ms.openlocfilehash: 18b0f036e49996564aa68735300f4e677ce5b1cb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780233"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planifier des réunions de grande taille dans Skype entreprise Server
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les meilleures pratiques pour la mise en œuvre et la gestion de grandes réunions dans Skype entreprise Server.
  
La taille des réunions que Skype entreprise Server peut prendre en charge dépend du fait que la Conférence est hébergée sur un pool partagé ou dédié : depuis 250 participants d’un pool partagé vers 1000 participants sur un pool dédié. 
  
> [!NOTE]
> Cette rubrique est axée sur les meilleures pratiques pour les grandes réunions prises en charge par Skype entreprise Server. Si votre organisation requiert des capacités de réunion plus importantes, vous devez envisager d’implémenter un environnement hybride qui tire parti de la diffusion de réunion Skype, un nouveau service en ligne qui fait partie d’Office 365. 

> [!NOTE]
> La diffusion de réunion Skype permet aux utilisateurs d’héberger et de diffuser des réunions à un grand public en ligne, jusqu’à 10 000 participants. L’utilisation de la diffusion de réunion Skype nécessite que Skype entreprise Server soit déjà configuré dans une installation hybride avec une organisation Office de production 365. Tous les utilisateurs doivent disposer d’un client en ligne établi en tant que composant requis. Si vous souhaitez déployer une solution hybride pouvant tirer parti de la diffusion de réunion Skype, consultez la rubrique [qu’est-ce qu’une diffusion de réunion Skype ?](https://go.microsoft.com/fwlink/?LinkId=617071) et [configurez votre déploiement local pour la diffusion de réunion Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Les grandes réunions ont généralement les caractéristiques suivantes :
  
- Le format de la réunion est celui d’une présentation un-à-plusieurs.
    
- Un ou plusieurs utilisateurs constituent les présentateurs. Le reste de l’assistance constitue les participants.
    
- Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.
    
- L’audio est nécessaire et la vidéo peut également être utilisée.
    
- Une personne dédiée, généralement l’organisateur de la réunion ou un assistant de l’organisateur, configure la réunion bien à l’avance.
    
- Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, le cas échéant.
    
Lorsqu’un utilisateur planifie une réunion, Skype entreprise Server crée un enregistrement dans la base de données de conférence, qui stocke les données de conférence, mais ne réserve pas de ressources matérielles pour la réunion planifiée à l’avance. Au lieu de cela, Skype entreprise Server dispose d’une logique d’équilibrage de charge intégrée pour allouer dynamiquement les ressources de conférence sur les serveurs frontaux de manière à distribuer équitablement les charges sur tous les serveurs frontaux du pool. Cela met en place et utilise efficacement les ressources matérielles, mais il est important de planifier correctement les réunions de très grande taille. 
  
Par exemple, lorsqu’un pool Skype entreprise Server est en cours d’exécution proche de sa capacité maximale, chaque serveur frontal peut héberger approximativement 125 réunions de taille moyenne. L’ajout d’une autre petite réunion ne serait pas un problème, mais l’ajout d’une réunion pour 1000 utilisateurs serait un problème, car les serveurs frontaux ne seraient probablement pas en mesure de prendre en charge une réunion de grande taille en même temps que les autres réunions 125.
  
La prise en charge de grandes réunions allant jusqu’à 1000 participants nécessite de traiter les problèmes liés au modèle matériel partagé et au modèle no-reservation. En règle générale, vous devez planifier un pool dédié et suivre les meilleures pratiques, comme décrit dans les sections suivantes. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planifier un pool dédié

Si votre organisation a besoin de réunions avec plus de 250 participants, vous devez planifier un pool dédié pour prendre en charge la charge. 
  
Pour disposer de ressources d’UC et de mémoire suffisantes pour les réunions allant jusqu’à 1000 utilisateurs, les serveurs frontaux d’hébergement ne doivent pas héberger de messagerie instantanée et de présence ou de charges de travail voix entreprise. Les serveurs ne doivent pas non plus héberger d’autres réunions, quelle que soit la taille des autres réunions. Pour héberger jusqu’à 1000 utilisateurs, vous devez configurer un pool Skype entreprise Server distinct dédié à l’hébergement de grandes réunions.
  
Un pool Skype entreprise Server dédié à l’hébergement de grandes réunions ne doit héberger qu’une seule réunion d’un maximum de 1000 utilisateurs en même temps, de sorte que les heures de réunion doivent être réservées à l’avance via un processus de planification hors bande pour garantir un support dédié à partir des serveurs frontaux. Pour prendre en charge plusieurs grandes réunions en même temps, vous devez configurer plusieurs pools de réunions de grande taille dédiés.
  
Pour plus d’informations sur la configuration matérielle et logicielle requise, ainsi que sur la planification d’une topologie qui prend en charge les grandes réunions, reportez-vous à [Hardware and Software Requirements for Conferencing in Skype for Business Server](hardware-and-software-requirements.md) et [plan Your Conferencing Topology for Skype for Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Mettre en œuvre les meilleures pratiques pour les grandes réunions

Après avoir configuré un pool dédié pour les grandes réunions, vous pouvez prendre des mesures pour vous assurer que les grandes réunions hébergées dans le pool fournissent la meilleure expérience utilisateur. Les sections suivantes fournissent des instructions pour la gestion des grandes réunions :
  
- Créer des organisateurs de réunions dédiés
    
- Créer des modérateurs dédiés
    
- Tenir à jour un calendrier distinct pour les grandes réunions
    
- Mettre en œuvre un processus de planification des réunions de grande taille
    
- Spécification des détails de planification appropriés
    
- Créer une stratégie de conférence pour les grandes réunions
    
### <a name="create-dedicated-meeting-organizers"></a>Créer des organisateurs de réunions dédiés

Pour réduire le trafic de communications en temps réel dans le pool de réunions de grande taille, Microsoft ne recommande pas d’héberger des utilisateurs qui se connectent régulièrement à l’aide de clients Skype entreprise et qui participent à des sessions de messagerie instantanée, de présence, de conférence et de voix. Au lieu de cela, effectuez l’une des opérations suivantes :
  
- Créer un ou plusieurs comptes d’utilisateurs dédiés uniquement pour la planification des grandes réunions
    
- Accueil les comptes d’utilisateur du personnel responsable de la planification des grandes réunions dans un pool de réunions de grande taille
    
### <a name="create-dedicated-moderators"></a>Créer des modérateurs dédiés

Avec plusieurs centaines à un millier d’utilisateurs dans une réunion, il est recommandé de faire en sorte qu’une personne dédiée ait modéré la session en ligne d’une grande réunion. Cette personne dédiée peut être déléguée de l’organisateur de la réunion ou d’un membre du personnel du support technique pour les grandes réunions de l’organisation. Il est important d’ajouter le modérateur de réunion dédié comme présentateur au moment où la réunion est programmée, même s’il soit possible de promouvoir un participant de la réunion en ligne au rôle de présentateur pendant la réunion.
  
Le modérateur de la réunion peut utiliser toutes les fonctionnalités du présentateur des clients Skype entreprise pour gérer la grande réunion. Ces fonctionnalités sont les suivantes :
  
- Surveillance de la salle d’attente et admission ou rejet des utilisateurs dans la salle d’attente
    
- Suppression des utilisateurs de la réunion qui ne doivent pas être en réunion
    
- Modification des types d’accès aux réunions
    
- Modification des rôles des participants
    
- Invitation de participants supplémentaires lors de la réunion à l’aide de la fonction glisser-déplacer, de la numérotation téléphonique ou de la messagerie
    
- Activation et désactivation de la désactivation de l’audience ou des utilisateurs individuels
    
- Gestion du contenu de réunion, y compris le téléchargement de contenu, la suppression de contenu et le changement de contenu actif

    
### <a name="maintain-a-separate-calendar"></a>Tenir à jour un calendrier distinct

Pour chaque pool de réunions de grande taille, vous devez conserver un calendrier distinct des grandes réunions planifiées sur ce pool. Par exemple, vous pouvez créer un compte d’utilisateur unique sur le pool de réunions de grande taille et utiliser Outlook avec Exchange et le complément de réunion en ligne pour Skype entreprise afin de conserver un calendrier distinct. Si vous utilisez plusieurs comptes d’utilisateurs pour permettre au personnel de support technique de créer des réunions de grande taille, vous pouvez configurer un calendrier distinct qui regroupe toutes les réunions de grande taille créées par les membres du personnel de support technique. 
  
La gestion d’un calendrier distinct des réunions de grande taille contribue à éviter les conflits et permet de s’assurer que seule une réunion de grande taille est active à un moment donné.
  
### <a name="implement-a-scheduling-process"></a>Mettre en œuvre un processus de planification

Étant donné qu’une seule grande réunion à la fois est prise en charge sur le pool de réunions dédié de grande taille, vous devez implémenter un processus de planification de réunion de grande taille afin de faciliter la configuration de grandes réunions et d’éviter les conflits. Cette fonctionnalité n’est pas fournie directement par les clients Skype entreprise Server ou Skype entreprise. Pour implémenter ce processus, vous pouvez utiliser le système de ticket de l’équipe de support de votre organisation, le cas échéant.
  
La planification d’une grande réunion implique d’effectuer les étapes suivantes :
  
- L’organisateur de réunion ou le délégué détermine l’heure, la durée et la taille d’une prochaine réunion, en plus de la liste de présentateurs. Si la taille de réunion anticipée dépasse 250 utilisateurs ou pour garantir la meilleure expérience pour une réunion de moins de 250 utilisateurs, l’organisateur ou le délégué soumet une demande pour une grande réunion.
    
- Le personnel en charge de la planification vérifie si la date et l’heure demandées sont disponibles. Comme nous ne prenons en charge qu’une seule grande réunion à la fois sur le pool dédié, le personnel de planification doit vérifier le calendrier de grandes réunions pour déterminer si une autre réunion est planifiée pour la date et l’heure demandées. Si l’heure demandée est disponible, le personnel approuve la demande de réunion.
    
- Si la demande est approuvée, le personnel de planification (à l’aide des informations d’identification sur le pool dédié) utilise le complément de réunion en ligne pour Skype entreprise avec Outlook pour configurer une réunion sur le pool dédié aux grandes réunions. L’URL à utiliser pour participer à la réunion est fournie par le demandeur dans le cadre de l’avis d’approbation.
    
- L’organisateur de la réunion ou le délégué utilise Outlook pour planifier la réunion à venir, en ajoutant l’URL permettant de joindre la réunion à l’invitation à la réunion. L’organisateur de réunion ou le délégué spécifie alors les utilisateurs à inviter et envoie les invitations à la réunion.
    
### <a name="specify-appropriate-scheduling-details"></a>Spécification des détails de planification appropriés

Après s’être assurée qu’aucune autre réunion n’est prévue à l’heure demandée, l’équipe de support des grandes réunions qui traite la demande planifie la réunion dans le pool de grandes réunions. 
  
Pour garantir une expérience utilisateur optimale, il est important de planifier la grande réunion avec les niveaux d’accès et les paramètres de réunion appropriés adaptés aux besoins de l’organisateur de la réunion. Examinez les paramètres de planification suivants configurés dans les options de réunion Skype entreprise :
  
- Utilisez un nouvel espace de réunion pour chaque grande réunion au lieu de réutiliser l’espace de réunion dédié. 
    
- Spécifiez le niveau d’accès à la réunion comme suit :
    
  - Si au moins un invité est externe à l’organisation, définissez le type d’accès à la réunion sur **tout le monde (aucune restriction)**. Cela vous évitera ainsi d’avoir à gérer une grande salle d’attente pendant le déroulement de la réunion.
    
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
    
    En gérant explicitement les présentateurs, vous pouvez limiter le nombre de présentateurs à un petit nombre suffisant pour qu’il soit possible d’avoir une grande réunion efficace. Si la majorité des participants à la réunion ont un rôle de participant, cela limite les chances de voir des personnes prendre accidentellement le contrôle de la présentation, supprimer une présentation PowerPoint, désactiver ou activer le son pour les présentateurs et perturber le déroulement de la réunion. 
    
- Cochez le paramètre **Désactiver le son pour tous les participants** pour faire en sorte que seuls les présentateurs puissent diffuser du son au cours de la réunion.
    
- Activez la case à cocher bloquer les paramètres **vidéo des participants** pour vous assurer que seuls les présentateurs peuvent diffuser la vidéo dans la réunion.
    
### <a name="create-a-conferencing-policy"></a>Créer une stratégie de conférence

Créez une stratégie de conférence spécialement pour les grandes réunions, puis affectez la stratégie de conférence aux utilisateurs hébergés sur le pool dédié aux grandes réunions. Configurez la stratégie de conférence avec les paramètres suivants :
  
- Définissez l’option **MaxMeetingSize** sur 1000. (La valeur par défaut est 250.)
    
- Définissez l’option **AllowLargeMeetings** à **True**. 
    
- Définissez l’option **EnableAppDesktopSharing** à **Aucun**.
    
- Définissez l’option **AllowUserToScheduleMeetingsWithAppSharing** à **False**.
    
- Définissez l’option **AllowSharedNotes** à **False**.
    
- Définissez l’option **AllowAnnotations** à **False**.
    
- Définissez l’option **DisablePowerPointAnnotations** à **True**.
    
- Définissez l’option **AllowMultiview** à **False**.
    
- Définissez l’option **EnableMultiviewJoin** à **False**.
    
> [!NOTE]
> La prise en charge des grandes réunions dans Skype entreprise Server nécessite la définition du paramètre **AllowLargeMeetings** sur true. Lorsque ce paramètre est défini sur true, l’expérience Skype entreprise est optimisée pour les réunions très grandes lorsque les utilisateurs rejoignent la réunion. Plus précisément, dans une grande réunion, Skype entreprise n’affiche pas la liste complète des participants à la réunion, ce qui constitue un goulot d’étranglement au niveau des performances pour le client et Skype entreprise Server. Au lieu de cela, Skype entreprise affiche uniquement les informations sur l’utilisateur et la liste des présentateurs de la réunion. Skype entreprise affiche toujours le nombre total de participants disponibles dans les grandes réunions.

Le paramètre **AllowLargeMeetings $true** provoque les éléments suivants :

- Masque la liste des participants. 

- Désactive les erreurs dans la fenêtre de messagerie instantanée.

- Désactive la vidéo multi-partie.

- Désactive la possibilité de promouvoir un participant au présentateur. Vous devez planifier avant et déclarer tous les présentateurs avant la réunion.

- Désactive la fonctionnalité de désactivation des participants individuels.

- Désactive la fonctionnalité de verrouillage de la vidéo pour les participants.

- Les utilisateurs distants RTC ne seront pas en mesure de les activer à l’aide de 6 car l’assistance virtuelle personnelle qui est responsable des commandes DTMF dans les grandes réunions actives est manquante.

- Si le présentateur/organisateur planifie une réunion où tout le monde doit être muet en premier (« muet »), les utilisateurs PSTN seront muets tout au long de l’appel et ne pourront pas les activer.

À l’exception du paramètre **Taille maximale de la réunion**, tous les autres paramètres de stratégie de conférence spécifiés ici sont requis afin de désactiver les fonctionnalités de conférence qui ne sont pas nécessaires pour les grandes réunions.
  
En outre, vous devez configurer le pool dédié aux grandes réunions de manière à ce que chaque utilisateur de Skype entreprise Server hébergé sur le pool et responsable de la gestion de la planification de la réunion dispose des autorisations appropriées. Pour ce faire, procédez ainsi :
  
- Définissez l’option **Désigné comme présentateur** à **Aucun**. En règle générale, un ou quelques utilisateurs parmi tous les participants sont des présentateurs, et les participants ne doivent pas être automatiquement admis dans des grandes réunions en tant que présentateurs. Les présentateurs doivent être explicitement désignés au moment de la planification de la réunion ou promus explicitement au cours de la réunion.
    
- Assurez-vous que la case à cocher **Type de conférence affecté par défaut** n’est pas sélectionnée. Ce paramètre contrôle si le complément de réunion en ligne pour Skype entreprise planifie toujours des conférences à l’aide de la Conférence affectée de l’organisateur, ce qui signifie que les réunions planifiées possèdent la même URL et les mêmes informations audio. Dans des scénarios de collaboration de petit groupe, l’utilisation de ce type de conférence est pratique, car tout le monde a sa conférence assignée individuelle et l’URL pour participer ainsi que les informations audio constantes permettent de rejoindre facilement la réunion. Cependant, dans des scénarios de grande réunion, l’équipe de support planifie les grandes réunions avec un ensemble d’informations d’identification d’utilisateur et fournit les URL et les informations audio aux demandeurs de la réunion. Dans ce cas, l’utilisation d’une URL différente pour rejoindre chaque réunion est préférable.
    
- Vérifiez que la case à cocher **Admettre les utilisateurs anonymes par défaut** n’est pas sélectionnée, sauf si elle est nécessaire. Ce paramètre affecte le type d’accès à la réunion par défaut planifié par le complément de réunion en ligne pour Skype entreprise lorsqu’une conférence n’est pas utilisée. L’option appropriée pour ce paramètre dépend des besoins de votre organisation. Si les grandes réunions de votre organisation sont des réunions internes, ne sélectionnez pas cette option. Si la plupart des grandes réunions nécessitent la participation d’utilisateurs externes, sélectionnez cette option.
    
Pour plus d’informations sur la création d’une stratégie de conférence, voir [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

