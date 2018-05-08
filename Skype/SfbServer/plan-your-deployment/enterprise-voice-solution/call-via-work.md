---
title: Planifier l’appel via le bureau dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planification des appels via le bureau dans Skype pour Business Server, ce qui permet l’intégration entre Skype pour les entreprises et votre système téléphonique PBX, afin que les utilisateurs peuvent utiliser Skype pour les entreprises à contrôler leurs téléphones PBX.
ms.openlocfilehash: 29c7c894d15621c0560eeef30ac7e5cbb28044fa
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-call-via-work-in-skype-for-business-server-2015"></a>Planifier l’appel via le bureau dans Skype Entreprise Server 2015
 
Planification des appels via le bureau dans Skype pour Business Server, ce qui permet l’intégration entre Skype pour les entreprises et votre système téléphonique PBX, afin que les utilisateurs peuvent utiliser Skype pour les entreprises à contrôler leurs téléphones PBX.
  
 **Appel via le bureau** est une nouvelle fonctionnalité dans Skype pour Business Server qui vous permet d’intégrer votre Skype pour une solution d’entreprise avec vos systèmes de téléphone PBX existants. Un utilisateur activé pour l’appel via le bureau, cliquez Skype pour les entreprises à appeler un autre utilisateur, soit au sein de votre déploiement ou d’un utilisateur externe. L’appel est effectué via le téléphone PBX de l’utilisateur. Cela permet à un utilisateur avec un téléphone PBX à inclure les paramètres audio dans leur riche Skype pour des conversations. Dans les versions précédentes d’appel distant Lync Server contrôle est une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype pour Business Server, cette fonctionnalité a été remplacée par un appel via le bureau.
  
Appel via le bureau permet à ce qui suit pour les utilisateurs de téléphone PBX
  
- Expérience cliquer pour appeler grâce à la fonctionnalité audio du téléphone PBX.
    
- Présence, recherche d’un utilisateur et l’intégration de messagerie instantanée--, par exemple, deux utilisateurs appel via le bureau dans une conversation par messagerie instantanée peuvent ajouter audio à sa session, avec le système audio fourni par le biais de téléphones PBX.
    
- Possibilité d’ajouter la messagerie instantanée, le partage d’application et le transfert de fichiers à un appel appel via le bureau.
    
- Participation à la réunion en un clic
    
## <a name="how-it-works"></a>Mode de fonctionnement

Appel via le bureau utilise Unified Communications Web API (UCWA) en tant que l’agent utilisateur DOS à DOS (B2BUA) entre le système PBX et votre Skype pour le déploiement de serveur d’entreprise, afin qu’aucune passerelle d’application (CSTA) informatique de télécommunications n’est nécessaire pour se connecter Skype pour Business Server avec votre système PBX. UCWA est un service introduit dans les versions précédentes de Lync Server pour activer la connectivité mobile et les clients web et est automatiquement installé sur chaque serveur frontal.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Appel de flux de travail pour un appel appel via le bureau

L’exemple suivant illustre comment un utilisateur activé pour l’appel via le bureau permettre utiliser le Skype pour Business Server pour émettre un appel :
  
![Affiche les étapes pendant un Appel via le bureau : l’appelant clique pour passer un appel à l’aide du client Skype Entreprise, puis UCWA fait sonner le téléphone de l’appelant. Lorsque celui-ci décroche, le destinataire est appelé.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. L’utilisateur sélectionne un utilisateur dans leur Skype pour client d’entreprise et clique sur l’icône téléphone pour appeler. Ou bien, durant une conversation de MI, l’utilisateur clique sur l’utilisateur avec lequel il partage la session.
    
2. Le téléphone PBX de l’appelant commence à sonner. L’ID d’appelant pour ce téléphone affiche un numéro de téléphone globale dont vous avez configuré à afficher dans l’ID d’appelant de passer des appels de l’appel via le bureau de tous les utilisateurs. Ce numéro de téléphone global n’est pas un véritable numéro correspondant au téléphone d’un individu. Il s’agit d’un signal visuel indiquant à un utilisateur que l’appel sortant lui appartient et ne correspond pas à un appel entrant survenant simultanément. Lorsque vous déployez des appels via le bureau, vous devez former les utilisateurs sur ce numéro de téléphone global et ce que signifie.
    
3. L’utilisateur appelant décroche son téléphone PBX. Skype pour les entreprises lance ensuite l’appel vocal à l’appelé. 
    
4. Lorsque l’appelant décroche, l’appel vocal commence. Si les deux utilisateurs étaient déjà dans une session de MI, elle peut se poursuivre.
    
### <a name="joining-a-conference-with-call-via-work"></a>Participation à une téléconférence via le bureau

Un utilisateur de l’appel via le bureau permettre participer à une réunion planifiée en cliquant sur l’URL de la réunion. Skype pour les entreprises affiche ensuite un message de **connexion à** jusqu'à ce que le service de conférence compose le téléphone PBX de l’utilisateur. L’utilisateur de l’appel via le bureau puis sélectionne le téléphone PBX et rejoint la réunion.
  
Un utilisateur de l’appel via le bureau peut également utiliser l’option **Conférence maintenant** dans Skype pour les entreprises pour créer des réunions Conférence maintenant. L’utilisateur voit alors le message **Appel sortant** et le téléphone PBX sonne.
  
Un utilisateur de l’appel via le bureau peut également se connecter à une réunion en appelant le numéro de pont de conférence à partir de Skype pour les entreprises. Si un code PIN de conférence est requis, l’utilisateur doit le composer sur son téléphone PBX.
  
### <a name="incoming-calls"></a>Appels entrants

Lorsqu’un utilisateur activé pour appel via le bureau reçoit un Skype pour l’appel de l’entreprise, le téléphone PBX et Skype de l’utilisateur pour les clients professionnels que tous les faire sonner simultanément (si l’utilisateur a configuré la sonnerie simultanée). L’utilisateur peut accepter l’appel en décrochant le téléphone PBX ou en cliquant sur **Accepter** dans la Skype pour Business notification. Si l’utilisateur accepte l’appel à l’aide de Skype pour les entreprises, le Skype pour la fenêtre d’entreprise pour l’appel reste ouverte. Mais si l’utilisateur accepte l’appel en décrochant le téléphone PBX, puis ferme le Skype pour la fenêtre de notification d’entreprise et il n’existe aucune Skype pour la session de l’entreprise, uniquement l’appel vocal sur le téléphone PBX.
  
Lorsqu’un utilisateur activé pour l’appel via le bureau reçoit un appel PBX, uniquement les sonneries de téléphone PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitations de l’appel via le bureau

Appel via le bureau est une solution vocale qui requiert la configuration matérielle peu, mais présente des limites par rapport aux fonctionnalités disponibles dans complète Enterprise Voice ou contrôle d’appel distant. Appel via le bureau présente les limitations suivantes :
  
- Si un utilisateur de l’appel via le bureau a configuré le transfert d’appel pour le numéro de rappel appel via le bureau et que quelqu'un essaie d’inviter cet utilisateur à une réunion par numéro de téléphone de l’utilisateur, l’invitation atteindra pas l’utilisateur. Vous devez recommander à vos utilisateurs de se servir des noms et non pas des numéros de téléphone pour adresser des invitations. 
    
- Fonctionnalité 911 améliorée et suivi des appels malveillants ne sont pas disponibles pendant un appel appel via le bureau.
    
- Les utilisateurs activés pour l’appel via le bureau ne peut pas utiliser la délégation, l’appel d’équipe ou les fonctionnalités de groupe de réponse.
    
- Les utilisateurs d’appeler via le travail ne peut pas utiliser Skype pour les entreprises pour enregistrer une réunion, désactiver ou activer le son de l’appel, maintenez la touche ou transférer l’appel ou mise en garde d’appels.
    
- Les utilisateurs ne peuvent pas utiliser appel via le bureau pour accéder à leurs messages de messagerie vocale PBX.
    
- Les utilisateurs d’appeler via le travail ne peuvent pas transformer une session en route en tant qu’un appel vocal à une conférence de collaboration qui inclut des communications comme tableau blanc vidéo, Powerpoint, ou une Note.
    
- Les utilisateurs d’appeler via le travail ne peut pas ajouter d’autres utilisateurs à un appel de personne-2.
    
- Pas de prise en charge de l’appariement de téléphone de bureau ou de plug-in VDI.
    
- Si un utilisateur effectue ou répond à un appel en utilisant le téléphone PBX (et ne pas à l’aide de la Skype pour la fenêtre de l’entreprise), il n’y aura aucun journal de l’appel.
    
- Si votre système PBX ne prend pas en charge **REFER with Replaces**, voici ce qui se produit. Sur un appel appel via le bureau, si l’utilisateur transfère l’appel en cours à partir du téléphone PBX, la fenêtre d’appel disparaîtra pas à partir de leur Skype pour la fenêtre de l’entreprise. Si l’utilisateur ferme ensuite la fenêtre d’appel, l’appel entre la cible de transfert et le cessionnaire prend fin. 
    
## <a name="prerequisites-for-call-via-work"></a>Conditions requises pour l’appel via le bureau

Pour activer des utilisateurs pour un appel via le bureau, vous devez disposer de certaines conditions préalables en place. Pour plus d’informations sur ces conditions préalables et pour savoir comment activer les utilisateurs pour l’appel via le bureau, voir [Déployer des appels via le bureau dans Skype pour Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Voir aussi

#### 

[Planifier le contrôle d’appel distant dans Skype pour Business 2015](remote-call-control.md)
  
[Déployer l’appel via le bureau dans Skype pour Business Server 2015](../../deploy/deploy-call-via-work.md)

