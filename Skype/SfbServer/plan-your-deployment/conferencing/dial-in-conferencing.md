---
title: Planifier la Conférence rendez-vous dans Skype entreprise Server
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
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Résumé : pour plus d’informations sur la planification de conférences rendez-vous dans Skype entreprise Server, voir les rubriques suivantes.'
ms.openlocfilehash: 90fe1ff1770d34b9fe0671de1a2fc0f9382acae5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815992"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Planifier la Conférence rendez-vous dans Skype entreprise Server
 
**Résumé :** Pour plus d’informations sur la planification de conférences rendez-vous dans Skype entreprise Server, reportez-vous à la rubrique.
  
La fonction de conférence rendez-vous est une fonctionnalité facultative de Skype entreprise Server qui permet aux participants d’une réunion de rejoindre la partie audio d’une réunion en appelant la réunion à partir d’un téléphone. Une conférence rendez-vous est un sous-ensemble d’une conférence audio nécessitant une configuration supplémentaire. Cette rubrique décrit la préparation du déploiement de la conférence rendez-vous pour votre organisation. 
  
Certains des composants requis pour les conférences rendez-vous sont spécifiques aux conférences rendez-vous, et certains sont des composants voix entreprise. Même si la conférence rendez-vous utilise une partie des mêmes composants que Voix Entreprise, vous pouvez la déployer même si vous ne déployez pas Voix Entreprise. Cette section présente les composants nécessaires pour la conférence rendez-vous. Pour plus d’informations sur la planification d’une solution voix entreprise complète, voir [planifier votre solution vocale d’entreprise dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
La conférence rendez-vous implique que vous indiquiez la connexion au réseau téléphonique commuté (RTC) en déployant un serveur de médiation. Vous devez également autoriser la conférence rendez-vous pour votre organisation :
  
- Préparation de la connexion au réseau téléphonique commuté (RTC)
    
- Préparation des plans de numérotation, des numéros d’accès et des régions de conférence
    
- Préparation de la création des annuaires de conférences
    
- Stratégie de conférence pour autoriser l’accès à la conférence rendez-vous
    
- Prise en charge des utilisateurs d’entreprise et des utilisateurs anonymes
    
> [!NOTE]
> Si vous déployez la Conférence rendez-vous, vous devez la déployer dans chaque liste de déploiement de Skype entreprise Server Conferencing. Il n’est pas nécessaire d’attribuer des numéros d’accès (numéros appelés par les participants à une conférence) à chaque pool, mais vous devez déployer la fonctionnalité Conférence rendez-vous dans chaque pool. Cette obligation prend en charge la fonctionnalité de nom enregistré quand un utilisateur appelle un numéro d’accès à partir d’un pool pour participer à une conférence Skype entreprise Server dans un autre pool. 
  
## <a name="plan-for-pstn-connectivity"></a>Planification de la connectivité RTC

La conférence rendez-vous nécessite au moins un serveur de médiation et une passerelle de réseau téléphonique commuté (RTC). 
  
Vous pouvez déployer un serveur de médiation dans un site central ou dans un site de succursale. Dans un site central, vous pouvez colocaliser un serveur de médiation sur un pool frontal ou un serveur Standard Edition ou vous pouvez le déployer sur un serveur ou un pool autonome. Dans un site de succursale, vous pouvez déployer un serveur de médiation sur un serveur autonome ou comme composant du serveur Survivable Branch Appliance.
  
Vous pouvez déployer une passerelle RTC dans un site central ou dans un site de succursale. Dans un site de succursale, la passerelle RTC peut être autonome ou un composant Survivable Branch Appliance.
  
Pour plus d’informations sur la configuration requise du serveur de médiation et de la passerelle RTC, consultez le [composant serveur de médiation dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), [déploiement d’un serveur de médiation dans le générateur de topologie de Skype entreprise Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)et [définition d’une passerelle dans le générateur de topologie de Skype entreprise Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Préparation des plans de numérotation, des numéros d’accès et des régions de conférence

Pour configurer la conférence rendez-vous, vous créez des plans de numérotation et des numéros d’accès à des conférences rendez-vous. Vous indiquez également des régions de numérotation qui associent un numéro d’accès de conférence rendez-vous avec ses plans de numérotation. En particulier :
  
- Les plans de numérotation représentent des ensembles de règles de normalisation qui spécifient le nombre et la séquence de chiffres d’un numéro de téléphone et qui transposent ce numéro au format E.164 standard requis pour le routage des appels.
    
- Les numéros d’accès aux conférences rendez-vous sont les numéros que les participants composent pour accéder à une conférence.
    
- Tout numéro d’accès à une conférence rendez-vous doit être associé à au moins un plan de numérotation. 
    
- Chaque plan de numérotation est associé à une région de conférence.
    
Lorsque vous créez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. Quand vous créez le numéro d’accès à la conférence rendez-vous, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.
  
Vous pouvez également spécifier son étendue : utilisateur, pool ou site. Chaque utilisateur est associé au plan de numérotation dans l’étendue la plus restreinte applicable à son cas. Par exemple, un utilisateur est affecté à un plan de numérotation de niveau utilisateur, le cas échéant. Si aucun plan de numérotation de niveau utilisateur ne s’applique, l’utilisateur est affecté à un plan de numérotation au niveau du pool. Si aucun plan de numérotation au niveau du pool ne s’applique, l’utilisateur est affecté à un plan de numérotation au niveau du site. Si aucun plan de numérotation au niveau du site ne s’applique, l’utilisateur est affecté à un plan de numérotation global. 
  
Avant de configurer les plans de numérotation, il est important de planifier le mode d’attribution de nom des régions et l’utilisation des régions. Les considérations suivantes s’appliquent aux régions de conférence rendez-vous :
  
- Une région constitue généralement une zone géographique associée à un bureau ou à un groupe de bureaux.
    
- Des langues sont associées aux numéros d’accès aux conférences rendez-vous. Si vous prenez en charge des zones géographiques comprenant plusieurs langues, vous devez déterminer le mode de définition des régions pour prendre en charge les différentes langues. Par exemple, vous pouvez définir différentes régions en associant une zone géographique et une langue ou définir une seule région en fonction de la zone géographique et disposer de différents numéros d’accès aux conférences rendez-vous pour chaque langue.
    
- Lorsqu’un utilisateur programme une réunion, par défaut, cette dernière utilise la région spécifiée dans le plan de numérotation de cet utilisateur.
    
- Par défaut, tous les numéros d’accès aux conférences rendez-vous de la région sont inclus dans l’invitation à la réunion.
    
- Il est important de nommer les régions de manière explicite. L’utilisateur peut recourir aux noms pour modifier une région de réunion afin que les différents numéros d’accès soient inclus dans l’invitation. (Lorsque les utilisateurs utilisent Outlook pour planifier une réunion, l’utilisateur utilise le complément réunion en ligne pour Skype entreprise pour modifier la région).
    
- Les régions doivent être désignées de sorte que tout invité souhaitant accéder à une conférence puisse visualiser un numéro d’accès local dans l’invitation.
    
- Vous pouvez configurer l’ordre dans lequel les numéros d’accès au sein d’une région apparaissent sur la page Paramètres de conférence rendez-vous (et, par conséquent, l’ordre dans lequel ils apparaissent dans l’invitation à la Conférence) à l’aide des applets de commande Skype entreprise Server Management Shell.
    
- Un utilisateur peut composer un numéro d’accès pour participer à une conférence rendez-vous en tout point du globe.
    
Pour plus d’informations sur la création d’un plan de numérotation, reportez-vous à la rubrique [création ou modification d’un plan de numérotation dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/dial-plans.md) et [création ou modification d’une règle de normalisation dans Skype entreprise](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Planification des annuaires des conférences

Les annuaires de conférences maintiennent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence lorsque vous utilisez Skype entreprise et l’ID de conférence numérique uniquement utilisé par un participant à la Conférence rendez-vous pour participer à la Conférence. Le format de l’ID de conférence est le suivant :
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>
```

La création de différents annuaires des conférences permet de s’assurer que les ID de conférences restent courts jusqu’à ce qu’une quantité importante de conférences ait été créée. Dans une organisation avec un nombre type de conférences par utilisateur, il est recommandé de créer un annuaire des conférences ne dépassant pas 999 utilisateurs dans le pool. Le respect de cette consigne permet en général de limiter le nombre des ID de conférences. Cependant, lorsque le nombre d’annuaires de conférences (tous pools confondus) dépasse 9, la longueur de l’ID de conférence augmente pour permettre la prise en charge de conférences supplémentaires.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planification d’une stratégie de conférence qui autorise les accès

Les conférences doivent être activées pour l’accès rendez-vous lorsque vous configurez des stratégies de conférence. Par défaut, l’invitation à une conférence pour les conférences activées pour les accès par modem comporte les informations suivantes :
  
- ID numérique de conférence identifiant la conférence
    
- Un ou plusieurs numéros d’accès RTC
    
- Lien vers une page Paramètres de conférence rendez-vous qui contient la liste complète des numéros d’accès avec leurs langues associées, un emplacement pour créer, réinitialiser ou débloquer les codes confidentiels et d’autres informations, comme les contrôles DTMF (numérotation en fréquences vocales)
    
Pour plus d’informations sur les stratégies de conférence, voir [configurer des conférences rendez-vous dans Skype entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) et [gérer des stratégies de conférence dans Skype entreprise Server](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Prise en charge des utilisateurs d’entreprise et des utilisateurs anonymes

La fonction de conférence rendez-vous est prise en charge pour les utilisateurs d’entreprise et les utilisateurs anonymes. Les utilisateurs d’entreprise ont accès aux informations d’identification des services de domaine Active Directory et aux comptes Skype entreprise Server au sein de leur organisation. Les utilisateurs anonymes ne disposent pas d’informations d’identification dans votre organisation. Dans le contexte de conférence rendez-vous, un utilisateur dans une organisation de partenaire fédéré qui utilise le RTC pour se connecter à une conférence est considéré comme un utilisateur anonyme. Pour la conférence rendez-vous, contrairement aux autres contextes, les utilisateurs fédérés ne sont pas authentifiés.
  
Les utilisateurs d’entreprise ou les organisateurs de conférence qui participent à une conférence activée pour l’accès par modem composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Si un organisateur n’a pas encore rejoint la réunion, les utilisateurs peuvent entrer leur extension de communications unifiées (ou leur numéro de téléphone complet) et leur code confidentiel ou attendre d’être admis par l’organisateur. L’organisateur de la réunion peut participer à la réunion en tant que tel en entrant seulement son code confidentiel. Le serveur frontal utilise l’association de l’extension du numéro de téléphone complet et du code confidentiel pour mapper de manière unique les utilisateurs d’entreprise à leurs informations d’identification Active Directory. Ils sont ainsi authentifiés et identifiés à l’aide de leur nom dans la conférence. Ils peuvent également adopter un rôle de conférence prédéfini par l’organisateur.
  
> [!NOTE]
> Les utilisateurs d’entreprise qui se connectent à partir d’un téléphone IP Office ou de Skype entreprise Server attendant ne sont pas invités à entrer leur numéro de téléphone, car ils sont déjà authentifiés. 
  
Les utilisateurs anonymes qui souhaitent participer à une conférence composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Les utilisateurs anonymes non identifiés sont également invités à enregistrer leur nom. Le nom enregistré identifie les utilisateurs non authentifiés au sein de la conférence. Les utilisateurs anonymes ne sont pas admis à la conférence tant qu’au moins un organisateur ou utilisateur authentifié ne l’a pas rejointe. Aucun rôle prédéfini ne peut leur être attribué.
  
> [!NOTE]
> Les utilisateurs d’entreprise qui décident de ne pas entrer leur numéro de téléphone ni leur code confidentiel ne sont pas considérés comme authentifiés. Ils sont invités à enregistrer leur nom et traités comme des utilisateurs anonymes dans la conférence. 
  
Lors de la planification d’une réunion, l’organisateur de la réunion peut décider de restreindre l’accès à la réunion en la fermant ou en la verrouillant. Dans ce cas, les utilisateurs appelants sont invités à s’authentifier. 
  
- S’ils échouent ou décident de ne pas s’authentifier, ils sont transférés vers la salle d’attente jusqu’à ce qu’un responsable les acceptent ou les refusent, ou jusqu’à ce qu’ils arrivent à expiration et soient déconnectés.
    
- Une fois admis dans une conférence, les utilisateurs d’appels entrants peuvent participer à la portion audio de la conférence et exécuter des commandes de numérotation en fréquences vocales (DTMF) à partir du clavier du téléphone.
    
- Les responsables de conférences rendez-vous peuvent exécuter des commandes DTMF pour admettre des personnes de la salle d’attente, activer ou désactiver le micro des participants, verrouiller ou déverrouiller la conférence et activer ou désactiver les annonces d’entrée et de sortie.
    
- Les organisateurs peuvent également utiliser une commande DTMF pour admettre toutes les personnes de la salle d’attente, ce qui a pour effet de modifier les autorisations de la réunion en autorisant toute personne qui rejoint ultérieurement la réunion. 
    
- Tous les participants d’appels entrants peuvent exécuter des commandes DTMF pour écouter l’aide, lire la liste de conférence ou désactiver eux-mêmes leur micro.
    
- Les participants d’appels entrants (qu’ils composent le numéro ou non à partir du RTC) entendent des annonces personnelles pendant la conférence, par exemple, si leur micro a été désactivé ou non, si la réunion est enregistrée ou si une personne attend dans la salle d’attente.
    
    > [!NOTE]
    > Les participants qui rejoignent la conférence en cliquant sur un lien au lieu de composer un numéro n’entendent pas les annonces personnelles. 
  

