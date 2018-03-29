---
title: Planifier l’appel via le bureau dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planification pour appeler Via le travail dans Skype pour Business Server, qui permet l’intégration entre Skype pour l’entreprise et de votre système téléphonique PBX, afin que les utilisateurs puissent utiliser Skype pour les entreprises à contrôler leurs téléphones PBX.
ms.openlocfilehash: d70ffb7cd46f5d2ffd7efe4db860f3a84ca34ef5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-via-work-in-skype-for-business-server-2015"></a>Planifier l’appel via le bureau dans Skype Entreprise Server 2015
 
Planification pour appeler Via le travail dans Skype pour Business Server, qui permet l’intégration entre Skype pour l’entreprise et de votre système téléphonique PBX, afin que les utilisateurs puissent utiliser Skype pour les entreprises à contrôler leurs téléphones PBX.
  
 **Appeler Via le travail** est une nouvelle fonctionnalité dans Skype pour Business Server qui vous permet d’intégrer votre Skype pour solution professionnelle avec vos systèmes de téléphone PBX existants. Cliquez sur un utilisateur activé pour appeler Via le travail dans Skype pour entreprises à l’appel d’un autre utilisateur, soit au sein de votre déploiement ou d’un utilisateur externe. L’appel est effectué via le téléphone PBX de l’utilisateur. Cela permet à un utilisateur avec un téléphone PBX inclure l’audio dans leur riche Skype pour des conversations. Dans les versions précédentes d’appel à distance de Lync Server contrôle était une fonctionnalité qui a permis aux utilisateurs de contrôler leur téléphone PBX avec Lync Server. Dans Skype pour le serveur de l’entreprise, cette fonctionnalité a été remplacée à appeler Via le travail.
  
Les informations suivantes pour les utilisateurs de téléphone PBX permet d’appeler Via le travail
  
- Expérience cliquer pour appeler grâce à la fonctionnalité audio du téléphone PBX.
    
- Présence, recherche de l’utilisateur et intégration de la messagerie instantanée--par exemple, deux utilisateurs d’appeler Via le travail dans une session de messagerie instantanée peuvent ajouter de l’audio à leur session, avec l’audio fourni par le biais de téléphones PBX.
    
- La possibilité d’ajouter de messagerie instantanée, le partage d’applications et le transfert de fichiers à un appel d’appeler Via le travail.
    
- Participation à la réunion en un clic
    
## <a name="how-it-works"></a>Mode de fonctionnement

Appeler Via le travail utilise Unified Communications Web API (UCWA) comme l’agent utilisateur DOS à DOS (B2BUA) entre le système PBX et votre Skype pour le déploiement du serveur de l’entreprise, afin qu’aucune passerelle d’application (CSTA) de télécommunications d’ordinateur pris en charge n’est nécessaire pour se connecter Skype pour Business Server avec votre système PBX. UCWA est un service introduit dans les versions précédentes de Lync Server pour activer la connectivité mobile et les clients web et est automatiquement installé sur chaque serveur frontal.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Appel de flux de travail pour un appel d’appeler Via le travail

L’exemple suivant illustre comment un utilisateur activé pour appeler Via le travail peut utiliser le Skype pour Business Server pour effectuer un appel :
  
![Affiche les étapes pendant un Appel via le bureau : l’appelant clique pour passer un appel à l’aide du client Skype Entreprise, puis UCWA fait sonner le téléphone de l’appelant. Lorsque celui-ci décroche, le destinataire est appelé.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. L’utilisateur sélectionne un utilisateur dans leur Skype pour client d’entreprise et clique sur l’icône de téléphone pour les appeler. Ou bien, durant une conversation de MI, l’utilisateur clique sur l’utilisateur avec lequel il partage la session.
    
2. Le téléphone PBX de l’appelant commence à sonner. L’ID d’appelant pour ce téléphone affiche un numéro de téléphone global que vous avez configuré pour afficher l’ID de l’appelant de placer des appels de l’appeler Via le travail de tous les utilisateurs. Ce numéro de téléphone global n’est pas un véritable numéro correspondant au téléphone d’un individu. Il s’agit d’un signal visuel indiquant à un utilisateur que l’appel sortant lui appartient et ne correspond pas à un appel entrant survenant simultanément. Lorsque vous déployez appeler Via le travail, vous devez former les utilisateurs sur ce numéro de téléphone global et ce que cela signifie.
    
3. L’utilisateur appelant décroche son téléphone PBX. Skype pour entreprise lance alors l’appel vocal à l’appelé. 
    
4. Lorsque l’appelant décroche, l’appel vocal commence. Si les deux utilisateurs étaient déjà dans une session de MI, elle peut se poursuivre.
    
### <a name="joining-a-conference-with-call-via-work"></a>Participation à une téléconférence via le bureau

Un utilisateur de l’appeler Via le travail peut se joindre à une réunion planifiée en cliquant sur l’URL de la réunion. Skype pour entreprise affiche ensuite un message de **connexion à** jusqu'à ce que le service de réunion compose le téléphone PBX de l’utilisateur. L’utilisateur d’appeler Via le travail puis récupère le téléphone PBX et rejoint la réunion.
  
Un utilisateur d’appeler Via le travail pouvez également utiliser l’option **Conférence maintenant** dans Skype pour entreprise pour créer des réunions Conférence maintenant. L’utilisateur voit alors le message **Appel sortant** et le téléphone PBX sonne.
  
Un utilisateur d’appeler Via le travail peut également se connecter à une réunion en appelant le pont de conférence comprise dans Skype pour les entreprises. Si un code PIN de conférence est requis, l’utilisateur doit le composer sur son téléphone PBX.
  
### <a name="incoming-calls"></a>Appels entrants

Lorsqu’un utilisateur activé pour appeler Via le travail reçoit un Skype pour appel métier et le téléphone PBX de Skype l’utilisateur pour les clients d’entreprise que toutes simultanément (si l’utilisateur a paramétré sur sonnerie simultanée) de l’anneau. L’utilisateur peut accepter l’appel par le téléphone PBX prélèvement ou en cliquant sur **Accepter** sur le Skype pour la notification de l’entreprise. Si l’utilisateur accepte l’appel à l’aide de Skype pour les entreprises, le Skype pour fenêtre d’entreprise pour l’appel reste ouverte. Mais, si l’utilisateur accepte l’appel par le téléphone PBX prélèvement, puis le Skype pour la fenêtre de Business notification se ferme et il n’y a aucun Skype pour session Business, seul l’appel vocal via le téléphone PBX.
  
Quand un utilisateur activé pour appeler Via le travail reçoit un appel PBX, uniquement le PBX téléphone sonne.
  
## <a name="limitations-of-call-via-work"></a>Limitations des appels Via le travail

Appeler Via le travail est une solution vocale qui requiert l’installation du matériel peu, mais elle est limitée par rapport aux fonctionnalités disponibles dans les Voix Entreprise complète ou de contrôle d’appel distant. Appeler Via le travail présente les limitations suivantes :
  
- Si un utilisateur d’appeler Via le travail a configuré le transfert d’appel vers le numéro de rappel appeler Via le travail et que quelqu'un tente d’inviter cet utilisateur à une réunion par numéro de téléphone de l’utilisateur, l’invitation n’atteindront pas l’utilisateur. Vous devez recommander à vos utilisateurs de se servir des noms et non pas des numéros de téléphone pour adresser des invitations. 
    
- Fonctionnalité 911 améliorée et suivi des appels malveillants ne sont pas disponibles pendant les appels de l’appeler Via le travail.
    
- Les utilisateurs activés pour appeler Via le travail ne peut pas utiliser la délégation, appel d’équipe ou des fonctionnalités de groupe de réponse.
    
- Les utilisateurs d’appeler Via le travail Impossible d’utiliser Skype pour les entreprises à enregistrer une réunion, Muet ou désactiver l’appel, maintenez transférer l’appel ou utiliser le parc de l’appel.
    
- Les utilisateurs ne peuvent pas utiliser appeler Via le travail à accéder à leurs messages de messagerie vocale du PBX.
    
- Les utilisateurs des appeler Via le travail ne peut pas procéder à une session qui a été lancée comme un appel vocal à une conférence de collaboration qui inclut des communications comme tableau blanc de vidéo, Powerpoint, ou une remarque.
    
- Les utilisateurs des appeler Via le travail ne peut pas ajouter d’autres utilisateurs à un appel de 2 personnes.
    
- Pas de prise en charge de l’appariement de téléphone de bureau ou de plug-in VDI.
    
- Si un utilisateur effectue ou répond à un appel en utilisant le téléphone PBX (et ne pas à l’aide de la Skype pour fenêtre d’entreprise), il n’y aura aucun journal de l’appel.
    
- Si votre système PBX ne prend pas en charge **REFER with Replaces**, voici ce qui se produit. Tandis que lors d’un appel d’appeler Via le travail, si l’utilisateur transfère l’appel en cours à partir du téléphone du PBX, la fenêtre d’appel ne disparaîtra pas à partir de leur Skype pour la fenêtre de l’entreprise. Si l’utilisateur ferme ensuite la fenêtre d’appel, l’appel entre la cible de transfert et le cessionnaire prend fin. 
    
## <a name="prerequisites-for-call-via-work"></a>Conditions requises pour un appel Via le travail

Pour activer les utilisateurs pour appeler Via le travail, vous devez disposer de certaines conditions préalables en place. Pour plus d’informations sur ces conditions préalables et pour savoir comment activer les utilisateurs pour appeler Via le travail, voir [Déployer appeler Via le travail dans Skype pour Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Voir aussi

#### 

[Plan pour contrôle d’appel distant dans Skype pour entreprise 2015](remote-call-control.md)
  
[Déployer l’appel Via le travail dans Skype pour Business Server 2015](../../deploy/deploy-call-via-work.md)

