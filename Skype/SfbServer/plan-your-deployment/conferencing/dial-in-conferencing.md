---
title: Planifier les conférences téléphoniques dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la planification des conférences Skype Entreprise Server.'
ms.openlocfilehash: 1840133072e6bac5cf9b95597b8f23ed5d37a7bd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394976"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Planifier les conférences téléphoniques dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur la planification de la conférence Skype Entreprise Server.
  
La conférence rendez-vous est une fonctionnalité facultative de Skype Entreprise Server qui permet aux participants de participer à la partie audio d’une réunion en appelant à la réunion à partir d’un téléphone. Une conférence rendez-vous est un sous-ensemble d’une audioconférence et nécessite une configuration supplémentaire. Cette rubrique décrit ce à quoi vous devez penser avant de déployer la conférence téléphonique pour votre organisation. 
  
Certains des composants requis pour les conférences téléphoniques sont spécifiques à la conférence téléphonique et d’autres Voix Entreprise composants. Bien que la conférence dial-in utilise certains des mêmes composants que Voix Entreprise, vous pouvez déployer la conférence dial-in même si vous ne déployez pas Voix Entreprise. Cette section décrit les composants nécessaires pour les conférences téléphoniques. Pour plus d’informations sur la planification d’une solution Voix Entreprise complète, voir [Planifier Voix Entreprise solution Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
La conférence téléphonique nécessite que vous fournissiez une connectivité au réseau téléphonique commuté (PSTN) en déployant un serveur de médiation. Outre le déploiement d’un serveur de médiation, vous devez tenir compte des considérations suivantes pour autoriser les conférences téléphoniques pour votre organisation :
  
- Votre plan de connexion au réseau téléphonique commuté (PSTN)
    
- Votre plan pour les plans de numérotation, les numéros d’accès et les régions de conférence
    
- Votre plan de création d’annuaires de conférence
    
- Votre stratégie de conférence pour autoriser l’accès à la conférence
    
- Prise en charge des utilisateurs d’entreprise et anonymes
    
> [!NOTE]
> Si vous déployez la conférence téléphonique, vous devez la déployer dans chaque pool où vous déployez Skype Entreprise Server conférence. Il n’est pas nécessaire d’affecter des numéros d’accès (les numéros appelés par les participants pour participer à une conférence) dans chaque pool, mais vous devez déployer la fonctionnalité d’accès dans chaque pool. Cette exigence prend en charge la fonctionnalité de nom enregistré lorsqu’un utilisateur appelle un numéro d’accès à partir d’un pool pour participer Skype Entreprise Server conférence dans un autre pool. 
  
## <a name="plan-for-pstn-connectivity"></a>Planifier la connectivité PSTN

La conférence téléphonique nécessite au moins un serveur de médiation et au moins une passerelle de réseau téléphonique commuté (PSTN). 
  
Vous pouvez déployer un serveur de médiation dans un site central ou dans un site de succursale. Dans un site central, vous pouvez céquequer un serveur de médiation sur un pool frontal ou un serveur Édition Standard, ou vous pouvez le déployer sur un serveur ou un pool autonome. Dans un site de succursale, vous pouvez déployer un serveur de médiation sur un serveur autonome ou en tant que composant du Survivable Branch Appliance.
  
Vous pouvez déployer une passerelle PSTN dans un site central ou dans un site de succursale. Dans un site de succursale, la passerelle PSTN peut être autonome ou un composant du Survivable Branch Appliance.
  
Pour plus d’informations sur les conditions requises pour le serveur de médiation et la passerelle PSTN, voir Composant du serveur de médiation dans [Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), Déployer un serveur de médiation dans le Générateur de topologies dans [Skype Entreprise Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) et Définir une passerelle dans le Générateur de topologies dans [ Skype Entreprise Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Planifier les plans de numérotation, les numéros d’accès et les régions de conférence

Pour configurer la conférence téléphonique, vous devez créer des plans de numérotation et des numéros d’accès aux conférences. Vous spécifiez également les régions de numérotation qui associent un numéro d’accès de conférence à ses plans de numérotation. Plus particulièrement :
  
- Les plans de numérotation sont des ensembles de règles de normalisation qui spécifient le numéro et le modèle de chiffres dans un numéro de téléphone et traduisent le numéro de téléphone au format E.164 standard requis pour le routage des appels.
    
- Les numéros d’accès aux conférences téléphoniques sont les numéros que les participants appellent pour participer à une conférence.
    
- Chaque numéro d’accès aux conférences téléphoniques doit être associé à au moins un plan de numérotation. 
    
- Chaque plan de numérotation est associé à une région de conférence.
    
Lorsque vous créez un plan de numérotation, vous spécifiez la région de conférence qui s’applique au plan de numérotation. Lorsque vous créez le numéro d’accès, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.
  
Vous spécifiez également l’étendue du plan de numérotation : étendue utilisateur, étendue du pool ou étendue du site. Le plan de numérotation de l’étendue la plus étroite qui s’applique à l’utilisateur est attribué à chaque utilisateur. Par exemple, un plan de numérotation au niveau de l’utilisateur est affecté à un utilisateur, si un plan s’applique. Si un plan de numérotation au niveau de l’utilisateur ne s’applique pas, un plan de numérotation au niveau du pool est affecté à l’utilisateur. Si un plan de numérotation au niveau du pool ne s’applique pas, un plan de numérotation au niveau du site est affecté à l’utilisateur. Si un plan de numérotation au niveau du site ne s’applique pas, le plan de numérotation global est attribué à l’utilisateur. 
  
Avant de configurer les plans de numérotation, il est important de planifier le nom et l’utilisation des régions. Les considérations suivantes s’appliquent aux régions de conférences téléphoniques :
  
- Une région est généralement une zone géographique associée à un bureau ou à un groupe de bureaux.
    
- Les langues sont associées aux numéros d’accès aux appels. Si vous prisez en charge des zones géographiques qui ont plusieurs langues, vous devez décider de la façon dont vous souhaitez définir des régions pour prendre en charge les langues multiples. Par exemple, vous pouvez définir plusieurs régions en fonction d’une combinaison de géographie et de langue, ou vous pouvez définir une région unique en fonction de la géographie et avoir des numéros d’accès pour chaque langue.
    
- Lorsqu’un utilisateur planifie une réunion, la réunion utilise par défaut la région spécifiée par le plan de numérotation de cet utilisateur.
    
- Par défaut, tous les numéros d’accès pour la région sont inclus dans l’invitation à la réunion.
    
- Il est important de nommer des régions afin qu’elles soient clairement reconnaissables. L’utilisateur peut utiliser les noms des régions pour modifier la région d’une réunion afin que différents numéros d’accès soient inclus dans l’invitation. (Lorsque les utilisateurs utilisent Outlook pour planifier une réunion, l’utilisateur utilise le Skype Entreprise réunion en ligne pour modifier la région).
    
- Les régions doivent être conçues pour que tous les invités qui souhaitent participer à une conférence voient un numéro d’accès local dans l’invitation à la conférence.
    
- Vous pouvez configurer l’ordre dans lequel les numéros d’accès au sein d’une région apparaissent sur la page Paramètres de conférences téléphoniques (et, par conséquent, l’ordre dans lequel ils apparaissent dans l’invitation à la conférence) à l’aide des cmdlets Skype Entreprise Server Management Shell.
    
- Tout utilisateur de n’importe quel emplacement peut appeler n’importe quel numéro d’accès pour participer à une conférence.
    
Pour plus d’informations sur la création d’un plan de numérotation, voir Créer ou modifier un plan de numérotation dans [Skype Entreprise Server](../../deploy/deploy-enterprise-voice/dial-plans.md) et Créer ou modifier une règle de normalisation [dans Skype Entreprise](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Planifier les annuaires des conférences

Les annuaires des conférences conservent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence lors de l’utilisation de Skype Entreprise et l’ID de conférence numérique uniquement qu’un participant à une conférence rendez-vous utilise pour participer à la conférence. Le format de l’ID de conférence est le suivant :
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


La création de plusieurs annuaires des conférences garantit que les ID de conférence resteront courts jusqu’à ce qu’une quantité importante de conférences soit créée. Dans une organisation avec un nombre typique de conférences par utilisateur, nous vous recommandons de créer un annuaire de conférences pour 999 utilisateurs dans le pool. À l’aide de cette recommandation, les ID de conférence peuvent généralement rester petits. Toutefois, une fois que le nombre d’annuaires des conférences (dans les pools) dépasse 9, le numéro d’ID de conférence augmente pour prendre en charge des conférences supplémentaires.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planifier une stratégie de conférence qui autorise l’accès à la conférence

Les conférences doivent être activées pour l’accès aux conférences lorsque vous configurez des stratégies de conférence. Par défaut, les conférences activées pour l’accès à la conférence incluent les informations suivantes dans l’invitation à la conférence :
  
- Un ID de conférence numérique qui identifie la conférence
    
- Un ou plusieurs numéros d’accès PSTN
    
- Lien vers une page de Paramètres de conférences téléphoniques, qui contient une liste complète des numéros d’accès avec leurs langues associées, un lieu de création, de réinitialisation ou de déblocage de numéros d’identification personnels (PIN) et d’autres informations, telles que des contrôles DTMF (numérotation en fréquences téléphoniques).
    
Pour plus d’informations sur les stratégies de conférence, voir [Configure dial-in conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) and [Manage conferencing policies in Skype Entreprise Server](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Prise en charge des utilisateurs d’entreprise et anonymes

La conférence téléphonique prend en charge à la fois les utilisateurs d’entreprise et les utilisateurs anonymes. Enterprise utilisateurs ont des informations d’identification des services de domaine Active Directory Skype Entreprise Server comptes au sein de leur organisation. Les utilisateurs anonymes n’ont pas d’informations d’identification d’entreprise au sein de votre organisation. Dans le contexte de conférence rendez-vous, un utilisateur de l’organisation d’un partenaire fédéré qui utilise le réseau téléphonique local (RST) pour se connecter à une conférence est traité comme un utilisateur anonyme. Pour les conférences téléphoniques, contrairement à d’autres contextes, les utilisateurs fédérés ne sont pas authentifiés.
  
Enterprise utilisateurs ou responsables de conférence qui rejoignent une conférence qui est activée pour l’accès entrant, composent l’un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Si un responsable n’a pas encore rejoint la réunion, les utilisateurs peuvent entrer leur poste de communications unifiées (ou leur numéro de téléphone complet) et leur code confidentiel ou attendre d’être admis par un responsable. L’organisateur de la réunion peut participer à la réunion en tant qu’organisateur en entrant simplement son code confidentiel. Le serveur frontal utilise la combinaison d’un numéro de téléphone complet ou d’une extension, et d’un code confidentiel, pour ma propres aux utilisateurs d’entreprise à leurs informations d’identification Active Directory. Par conséquent, les utilisateurs d’entreprise sont authentifiés et identifiés par leur nom dans la conférence. Enterprise utilisateurs peuvent également assumer un rôle de conférence prédéféré par l’organisateur.
  
> [!NOTE]
> Enterprise utilisateurs qui appellent à partir d’un téléphone IP de bureau ou d’un Skype Entreprise Server Ne sont pas invités à composer leur numéro de téléphone, car ils sont déjà authentifiés. 
  
Les utilisateurs anonymes qui souhaitent participer à une conférence entrante composent l’un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Les utilisateurs anonymes non authentifiés sont également invités à enregistrer leur nom. Le nom enregistré identifie les utilisateurs non authentifiés dans la conférence. Les utilisateurs anonymes ne sont pas admis à la conférence tant qu’au moins un dirigeant ou un utilisateur authentifié n’a pas rejoint la conférence et qu’un rôle prédéféré ne leur est pas attribué.
  
> [!NOTE]
> Enterprise utilisateurs qui choisissent de ne pas entrer leur numéro de téléphone et leur code confidentiel ne sont pas authentifiés. Ils sont invités à enregistrer leur nom et sont traités comme des utilisateurs anonymes dans la conférence. 
  
Lors de la planification d’une réunion, l’organisateur de la réunion peut choisir de restreindre l’accès à la réunion en rendant la réunion fermée ou verrouillée. Dans ce cas, les utilisateurs de connexion sont invités à s’authentifier. 
  
- Si les utilisateurs d’appels sortants échouent ou choisissent de ne pas s’authentifier, ils sont transférés vers la salle d’accueil où ils sont transférés jusqu’à ce qu’un responsable les accepte ou les rejette, ou qu’ils délai d’authentification et soient déconnectés.
    
- Une fois admis à une conférence, les utilisateurs d’appels peuvent participer à la partie audio de la conférence et peuvent utiliser des commandes DTMF (numérotation en fréquences vocales) à l’aide du clavier du téléphone.
    
- Les chefs d’accès peuvent utiliser des commandes DTMF pour activer ou désactiver la fonction d’entrée et de sortie des participants, verrouiller ou déverrouiller la conférence, admettre des personnes de la salle d’accueil et activer ou désactiver les annonces d’entrée et de sortie.
    
- Les responsables peuvent également utiliser une commande DTMF pour admettre tout le monde dans la salle d’accueil, ce qui modifie les autorisations de la réunion pour autoriser toute personne qui rejoint ensuite la réunion. 
    
- Tous les participants à la conférence peuvent utiliser des commandes DTMF pour écouter l’aide, écouter la liste des conférences et désactiver eux-mêmes le son.
    
- Les participants à une conférence rendez-vous (c’est-à-dire, qu’ils viennent ou non du PSTN) entendent des annonces personnelles pendant la conférence, par exemple, s’ils ont été mis en sourdine ou non, si la réunion est enregistrée ou si quelqu’un attend dans la salle d’attente.
    
    > [!NOTE]
    > Les participants qui rejoignent la conférence en cliquant sur un lien au lieu d’appeler n’entendent pas les annonces personnelles. 
  

