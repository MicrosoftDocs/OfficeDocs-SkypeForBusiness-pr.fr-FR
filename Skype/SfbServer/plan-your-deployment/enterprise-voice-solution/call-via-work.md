---
title: Planifier un appel via le travail dans Skype entreprise Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planifiez vos appels via le travail dans Skype entreprise Server, qui permet d’intégrer Skype entreprise et votre système téléphonique PBX, de sorte que les utilisateurs puissent utiliser Skype entreprise pour contrôler leurs téléphones PBX.
ms.openlocfilehash: 38c61145dcad609c75e7b2e3433efee307f8dc28
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803154"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planifier un appel via le travail dans Skype entreprise Server
 
Planifiez vos appels via le travail dans Skype entreprise Server, qui permet d’intégrer Skype entreprise et votre système téléphonique PBX, de sorte que les utilisateurs puissent utiliser Skype entreprise pour contrôler leurs téléphones PBX.
  
 L' **appel par le biais du travail** est une nouvelle fonctionnalité de Skype entreprise Server qui vous permet d’intégrer votre solution Skype entreprise à vos systèmes de téléphonie PBX existants. Un utilisateur ayant activé les appels via le travail peut cliquer dans Skype entreprise pour appeler un autre utilisateur, au sein de votre déploiement ou d’un utilisateur externe. L’appel est effectué via le téléphone PBX de l’utilisateur. Cela permet à l’utilisateur d’un téléphone PBX d’inclure le son dans ses conversations Skype entreprise complètes. Dans les versions précédentes du contrôle d’appel distant de Lync Server est une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype entreprise Server, cette fonction a été remplacée par un appel via le travail.
  
L’appel par le biais de votre bureau permet aux utilisateurs de téléphones PBX de procéder comme suit :
  
- Expérience cliquer pour appeler grâce à la fonctionnalité audio du téléphone PBX.
    
- Présence, recherche utilisateur et intégration de la messagerie instantanée (par exemple, deux appels via les utilisateurs professionnels dans une session de messagerie instantanée) peuvent ajouter de l’audio à leur session en utilisant le son fourni par les téléphones PBX.
    
- La possibilité d’ajouter la messagerie instantanée, le partage d’application et le transfert de fichiers à un appel via un appel de bureau.
    
- Participation à la réunion en un clic
    
## <a name="how-it-works"></a>Mode de fonctionnement

Appel par travail utilise l’API UCWA (Unified Communications Web API) en tant qu’agent utilisateur principal (B2BUA) entre le système PBX et votre déploiement Skype entreprise Server, de sorte qu’aucune passerelle CSTA (User-Supported Telecommunication application) n’est nécessaire pour se connecter. Skype entreprise Server avec votre système PBX. UCWA est un service présenté dans les versions précédentes de Lync Server pour permettre la connectivité avec les clients mobiles et Web, et est automatiquement installé sur chaque serveur frontal.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Flux de travail d’appel pour un appel via un appel

L’exemple suivant illustre la manière dont un utilisateur a activé les appels via le travail peut utiliser Skype entreprise Server pour passer un appel :
  
![Affiche les étapes pendant un Appel via le bureau : l’appelant clique pour passer un appel à l’aide du client Skype Entreprise, puis UCWA fait sonner le téléphone de l’appelant. Lorsque celui-ci décroche, le destinataire est appelé.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. L’utilisateur sélectionne un utilisateur dans son client Skype entreprise, puis clique sur l’icône du téléphone pour l’appeler. Ou bien, durant une conversation de MI, l’utilisateur clique sur l’utilisateur avec lequel il partage la session.
    
2. Le téléphone PBX de l’appelant commence à sonner. L’identification de l’appelant pour ce téléphone affiche un numéro de téléphone global que vous avez configuré pour afficher l’ID d’appelant de tous les utilisateurs qui placent un appel par le biais d’appels professionnels. Ce numéro de téléphone global n’est pas un véritable numéro correspondant au téléphone d’un individu. Il s’agit d’un signal visuel indiquant à un utilisateur que l’appel sortant lui appartient et ne correspond pas à un appel entrant survenant simultanément. Lorsque vous déployez un appel par le biais de votre entreprise, vous devez éduquer les utilisateurs sur ce numéro de téléphone global et ce qu’il signifie.
    
3. L’utilisateur appelant décroche son téléphone PBX. Skype entreprise appelle alors l’appel vocal pour l’appelant. 
    
4. Lorsque l’appelant décroche, l’appel vocal commence. Si les deux utilisateurs étaient déjà dans une session de MI, elle peut se poursuivre.
    
### <a name="joining-a-conference-with-call-via-work"></a>Participation à une téléconférence via le bureau

Un appel via le Bureau peut rejoindre une réunion planifiée en cliquant sur l’URL de la réunion. Skype entreprise affiche alors un message **de numérotation jusqu’à** ce que le service de réunion appelle le téléphone PBX de l’utilisateur. L’appel via l’utilisateur professionnel sélectionne alors le téléphone PBX et joint la réunion.
  
Un appel via l’utilisateur professionnel peut également utiliser l’option **Conférence maintenant** dans Skype entreprise pour créer des réunions Conférence maintenant. L’utilisateur voit alors le message **Appel sortant** et le téléphone PBX sonne.
  
Un appel via l’utilisateur professionnel peut également appeler une réunion en appelant son numéro dans Skype entreprise. Si un code PIN de conférence est requis, l’utilisateur doit le composer sur son téléphone PBX.
  
### <a name="incoming-calls"></a>Appels entrants

Lorsqu’un utilisateur a activé l’appel par le biais du travail, il reçoit un appel Skype entreprise, le téléphone PBX ainsi que les clients Skype entreprise de l’utilisateur, tous les anneaux en même temps. L’utilisateur peut accepter l’appel en décrochant le téléphone PBX ou en cliquant sur **accepter** dans la notification Skype entreprise. Si l’utilisateur accepte l’appel avec Skype entreprise, la fenêtre Skype entreprise pour l’appel reste ouverte. Si l’utilisateur accepte l’appel en décrochant le téléphone PBX, la fenêtre de notification de Skype entreprise se ferme et il n’y a pas de session Skype entreprise, seul l’appel vocal sur le téléphone PBX.
  
Lorsqu’un utilisateur a activé l’appel via le Bureau reçoit un appel PBX, seul le téléphone PBX sonne.
  
## <a name="limitations-of-call-via-work"></a>Limitations d’appel via le Bureau

L’appel par le biais du Bureau est une solution vocale qui nécessite un minimum de configuration matérielle, mais qui comporte des limitations par rapport aux fonctionnalités disponibles dans le contrôle voix ou appels distant complet de l’entreprise. Les appels via le bureau sont soumis aux limitations suivantes :
  
- Si un appel via le téléphone de bureau a configuré le renvoi d’appel via le numéro de rappel professionnel et qu’une personne tente d’inviter cet utilisateur à une réunion à l’aide du numéro de téléphone de l’utilisateur, l’invitation n’atteint pas l’utilisateur. Vous devez recommander à vos utilisateurs de se servir des noms et non pas des numéros de téléphone pour adresser des invitations. 
    
- La fonctionnalité 911 améliorée et le suivi des appels malveillants ne sont pas disponibles lors de vos appels passés par le biais d’appels professionnels.
    
- Les utilisateurs activés pour les appels via le travail ne peuvent pas utiliser les fonctionnalités délégation, appel d’équipe ou Response Group.
    
- Les utilisateurs de l’appel via le Bureau ne peuvent pas utiliser Skype entreprise pour enregistrer une réunion, désactiver ou activer le son de l’appel, mettre en attente ou transférer l’appel ou utiliser le parc d’appels.
    
- Les utilisateurs ne peuvent pas utiliser les appels via le Bureau pour accéder à leurs messages vocaux PBX.
    
- Les utilisateurs de l’appel via le Bureau ne peuvent pas remonter une session qui a commencé en tant qu’appel vocal pour une réunion de collaboration qui inclut des communications telles que la vidéo, PowerPoint, le tableau blanc ou une note.
    
- Les utilisateurs de l’appel via le Bureau ne peuvent pas ajouter des utilisateurs à un appel de 2 personnes.
    
- Pas de prise en charge de l’appariement de téléphone de bureau ou de plug-in VDI.
    
- Si un utilisateur effectue ou répond à un appel à l’aide du téléphone PBX (sans utiliser la fenêtre Skype entreprise), il n’y a aucun journal de l’appel.
    
- Si votre système PBX ne prend pas en charge **REFER with Replaces**, voici ce qui se produit. Lorsque l’utilisateur transfère l’appel en cours sur un téléphone PBX lors d’un appel, la fenêtre d’appel ne disparaîtra pas de sa fenêtre Skype entreprise. Si l’utilisateur ferme ensuite la fenêtre d’appel, l’appel entre la cible de transfert et le cessionnaire prend fin. 
    
## <a name="prerequisites-for-call-via-work"></a>Prérequis pour les appels via le Bureau

Pour permettre aux utilisateurs d’appeler via le bureau, vous devez disposer de conditions préalables en vigueur. Pour plus d’informations sur ces éléments requis et pour savoir comment permettre aux utilisateurs d’appeler via le travail, voir [déployer des appels via le travail dans Skype entreprise Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Voir aussi

[Planifier le contrôle d’appel distant dans Skype entreprise](remote-call-control.md)
  
[Déployer l’appel via le bureau dans Skype Entreprise Server 2015](../../deploy/deploy-call-via-work.md)

