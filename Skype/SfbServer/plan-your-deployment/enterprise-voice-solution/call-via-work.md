---
title: Planifier l’appel via le Skype Entreprise Server
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
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planification de l’appel via le travail dans Skype Entreprise Server, qui permet l’intégration entre Skype Entreprise et votre système téléphonique PBX, afin que les utilisateurs peuvent utiliser Skype Entreprise pour contrôler leurs téléphones PBX.
ms.openlocfilehash: 268ee3a6caa7b304cc63b4e7e16c2a7565f9ced3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768562"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planifier l’appel via le Skype Entreprise Server
 
Planification de l’appel via le travail dans Skype Entreprise Server, qui permet l’intégration entre Skype Entreprise et votre système téléphonique PBX, afin que les utilisateurs peuvent utiliser Skype Entreprise pour contrôler leurs téléphones PBX.
  
 **L’appel** via le travail est une nouvelle fonctionnalité de Skype Entreprise Server qui vous permet d’intégrer votre solution Skype Entreprise à vos systèmes téléphoniques PBX existants. Un utilisateur activé pour l’appel via le travail peut cliquer dans Skype Entreprise pour appeler un autre utilisateur, au sein de votre déploiement ou un utilisateur externe. L’appel est effectué à l’aide du téléphone PBX de l’utilisateur. Cela permet à un utilisateur ayant un téléphone PBX d’inclure du contenu audio dans ses conversations Skype Entreprise riche. Dans les versions précédentes de Lync Server, le contrôle d’appel distant était une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype Entreprise Server, cette fonctionnalité a été remplacée par Appel via le travail.
  
L’appel via le travail active les données suivantes pour les utilisateurs de téléphone PBX
  
- Expérience d’appel en un clic, avec l’audio fourni via le téléphone PBX.
    
- Présence, recherche d’utilisateur et intégration de la messagerie instantanée: par exemple, deux utilisateurs d’Appel via le travail dans une session de messagerie instantanée peuvent ajouter de l’audio à leur session, avec l’audio fourni via les téléphones PBX.
    
- Possibilité d’ajouter la messagerie instantanée, le partage d’application et le transfert de fichiers à un appel d’appel via le travail.
    
- Fonctionnalité de rejoindre une réunion en un clic
    
## <a name="how-it-works"></a>Mode de fonctionnement

Call Via Work utilise unified Communications Web API (UCWA) en tant qu’agent utilisateur dos à dos (B2BUA) entre le système PBX et votre déploiement Skype Entreprise Server, de sorte qu’aucune passerelle CSTA (Unified Communications Application) prise en charge par l’ordinateur n’est nécessaire pour connecter des Skype Entreprise Server à votre système PBX. UCWA est un service introduit dans les versions précédentes de Lync Server pour activer la connectivité avec les clients mobiles et web et est automatiquement installé sur chaque serveur frontal.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flux de travail d’appel pour un appel via le travail

L’exemple suivant montre comment un utilisateur activé pour l’appel via le travail peut utiliser la Skype Entreprise Server pour effectuer un appel :
  
![Indique les étapes d’un appel via le lieu de travail ; tout d’abord, l’appelant clique pour appeler une personne dans le client Skype Entreprise client ; puis l’UCWA fait sonner le téléphone de l’appelant. Lorsque l’appelant prend le téléphone, le destinataire est appelé.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. L’utilisateur sélectionne un utilisateur dans son client Skype Entreprise client, puis clique sur l’icône du téléphone pour l’appeler. Ou, au cours d’une conversation par messagerie instantanée, l’utilisateur clique pour appeler l’utilisateur avec qui il a la session.
    
2. Le téléphone PBX de l’utilisateur qui a passé l’appel commence à sonner. L’ID de l’appelant pour ce téléphone affiche un numéro de téléphone global que vous avez installé pour l’afficher dans l’ID d’appelant de tous les utilisateurs passant des appels via le téléphone. Ce numéro de téléphone global n’est pas un numéro de téléphone réel qui correspond au téléphone d’une personne. Au lieu de cela, il s’agit d’un signal visuel pour indiquer à un utilisateur qu’il s’agit de son propre appel sortant, et non d’un appel entrant qui se produit en même temps. Lorsque vous déployez appel via le travail, vous devez informer ces utilisateurs de ce numéro de téléphone global et de ce qu’il signifie.
    
3. L’utilisateur qui a passé l’appel sélectionne son téléphone PBX. Skype Entreprise lance ensuite l’appel vocal à l’appelé. 
    
4. Lorsque l’appelé répond, l’appel vocal commence. Si les deux utilisateurs avaient déjà une session de messagerie instantanée en cours, elle peut continuer.
    
### <a name="joining-a-conference-with-call-via-work"></a>Rejoindre une conférence avec appel via le travail

Un utilisateur d’appel via le travail peut participer à une réunion programmée en cliquant sur l’URL de la réunion. Skype Entreprise affiche ensuite un **message** sortant jusqu’à ce que le service de réunion compose le téléphone PBX de l’utilisateur. L’utilisateur Appel via le travail sélectionne ensuite le téléphone PBX et rejoint la réunion.
  
Un utilisateur Appel via le  travail peut également utiliser l’option Conférence maintenant Skype Entreprise pour créer des réunions Conférence maintenant. L’utilisateur voit ensuite le **message** « Appel sortant » et le téléphone PBX sonne.
  
Un utilisateur d’appel via le travail peut également se rendre à une réunion en appelant le numéro pont de conférence depuis Skype Entreprise. Si un code confidentiel de conférence est requis, l’utilisateur doit utiliser son téléphone PBX pour entrer le code confidentiel.
  
### <a name="incoming-calls"></a>Appels entrants

Lorsqu’un utilisateur activé pour l’appel via le travail reçoit un appel Skype Entreprise, le téléphone PBX et les clients Skype Entreprise de l’utilisateur sonnent tous simultanément (si l’utilisateur a installé la sonnerie simultanée). L’utilisateur peut accepter l’appel en sélectionnant le téléphone PBX ou en cliquant sur **Accepter** sur la notification Skype Entreprise message. Si l’utilisateur accepte l’appel à l’Skype Entreprise, la fenêtre Skype Entreprise de l’appel reste ouverte. Toutefois, si l’utilisateur accepte l’appel en sélectionnant le téléphone PBX, la fenêtre de notification Skype Entreprise se ferme et il n’y a pas de session Skype Entreprise, uniquement l’appel vocal sur le téléphone PBX.
  
Lorsqu’un utilisateur activé pour l’appel via le réseau téléphonique reçoit un appel PBX, seul le téléphone PBX sonne.
  
## <a name="limitations-of-call-via-work"></a>Limitations de l’appel via le travail

Call Via Work est une solution vocale qui nécessite peu de configuration matérielle, mais présente des limitations par rapport aux fonctionnalités disponibles dans le contrôle d’appel Voix Entreprise ou distant. L’appel via le travail présente les limitations suivantes :
  
- Si un utilisateur d’appel via le travail a mis en place le forwarding d’appel vers le numéro de rappel Appel via le travail et qu’une personne tente d’inviter cet utilisateur à une réunion par le numéro de téléphone de l’utilisateur, l’invitation n’atteint pas l’utilisateur. Vous devez informer vos utilisateurs afin qu’ils invitent les participants aux réunions en cliquant sur le nom et non sur le numéro de téléphone. 
    
- La fonctionnalité 911 améliorée et le suivi des appels malveillants ne sont pas disponibles pendant les appels d’appel via le lieu de travail.
    
- Les utilisateurs activés pour l’appel via le travail ne peuvent pas utiliser les fonctionnalités de délégation, d’appel d’équipe ou response group.
    
- Les utilisateurs d’Appel via le travail ne peuvent pas utiliser Skype Entreprise pour enregistrer une réunion, désactiver ou désactiver le son de l’appel, mettre en attente ou transférer l’appel, ou utiliser le parc d’appel.
    
- Les utilisateurs ne peuvent pas utiliser l’appel via le travail pour accéder à leurs messages vocaux PBX.
    
- Les utilisateurs d’Appel via le travail ne peuvent pas faire d’une session qui a commencé comme un appel vocal une réunion de collaboration qui inclut des communications telles que vidéo, Powerpoint, tableau blanc ou One Note.
    
- Les utilisateurs d’Appel via le travail ne peuvent pas ajouter d’utilisateurs à un appel à deux personnes.
    
- Aucune prise en charge du jumelage de téléphone de bureau ou du plug-in VDI.
    
- Si un utilisateur passe ou répond à un appel à l’aide du téléphone PBX (sans utiliser la fenêtre Skype Entreprise), il n’y aura aucun journal de l’appel.
    
- Si votre système PBX ne prend pas en **charge REFER avec replaces,** le comportement suivant se produit. Pendant un appel via le bureau, si l’utilisateur transfère l’appel en cours à partir du Téléphone PBX, la fenêtre d’appel ne disparaît pas de la fenêtre Skype Entreprise client. Si l’utilisateur ferme ensuite la fenêtre d’appel, l’appel entre la cible de transfert et le transfert se termine. 
    
## <a name="prerequisites-for-call-via-work"></a>Conditions préalables pour l’appel via le travail

Pour activer tous les utilisateurs pour l’appel via le travail, vous devez avoir des conditions préalables en place. Pour plus d’informations sur ces conditions préalables et pour savoir comment activer les utilisateurs pour l’appel via le travail, voir [Deploy Call Via Work in Skype Entreprise Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Voir aussi

[Planifier le contrôle d’appel distant dans Skype Entreprise](remote-call-control.md)
  
[Déploiement de l’appel via le Skype Entreprise Server 2015](../../deploy/deploy-call-via-work.md)

