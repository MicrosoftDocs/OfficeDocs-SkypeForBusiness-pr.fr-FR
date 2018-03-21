---
title: "Créer une file d’attente des appels système téléphonique"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 784033005882eeca105fd59a543ce9d1009ea84f
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2018
---
# <a name="create-a-phone-system-call-queue"></a>Créer une file d’attente des appels système téléphonique

Un appel système files d’attente contiennent des salutations utilisées lorsque quelqu'un appelle un numéro de téléphone pour votre organisation, la possibilité de faire automatiquement les appels en attente et la capacité de recherche pour l’agent d’appel disponible suivant gérer l’appel alors les personnes qui appel sont à l’écoute de la musique en attente. Vous pouvez créer une ou plusieurs files d’attente d’appel pour votre organisation.
  
Téléphone : appel système peuvent fournir des files d’attente :
  
- Un message d'accueil pour l'organisation
    
- Une attente musicale
    
- Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.
    
- Rendre les paramètres de taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.
    
Lorsque quelqu'un appelle à un numéro de téléphone qui a d’une file d’attente de l’appel, ils entendra un message d’accueil premier (si une est définie), puis il est placé dans la file d’attente et attend l’agent d’appel disponible suivant. L'appelant entendra une musique pendant la mise en attente et les téléopérateurs répondront dans l'ordre d'arrivée des appels ( *premier entré, premier sorti*  ).
  
Tous les appels en attente dans la file d’attente seront distribuées à l’aide d’une surveillance du routage en mode ou série routage :
  
- Surveillance du routage, le premier appel dans la file d’attente sonne tous les agents en même temps.
    
- Avec le routage de série, le premier appel dans la file d’attente sonne tous les agents d’appel un par un.
    
    > [!NOTE]
    > Agents d’appel qui sont **hors connexion**, ont défini de leur présence sur **ne pas déranger** ou qui ont choisi de renoncer à la file d’attente de l’appel ne sera pas appelés.
  
- Une seule notification d'appel entrant (pour l'appel en tête de file) sera envoyée aux téléopérateurs à la fois.
    
- Lorsqu'un téléopérateur accepte l'appel, le prochain appel entrant dans la file d'attente sonnera pour les autres téléopérateurs.
    
## <a name="step-1---getting-started"></a>Étape 1 : prise en main

Avant de commencer à utiliser les files d'attente d'appels, il est impératif de noter les points suivants :
  
- Une licence Enterprise E3 et **Système téléphonique** ou une licence Enterprise E5, votre organisation doit avoir (au minimum). Le nombre de licences d’utilisateur **Système téléphonique** affectées affecte le nombre de numéros de service sont disponibles pour être utilisés pour les files d’attente de l’appel. Le nombre de files d’attente de l’appel que peut avoir dépend du nombre de licences de **Système téléphonique** et **Les conférences Audio** qui vous sont affectées dans votre organisation. Pour en savoir plus sur les licences, allez [ici](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Pour rediriger les appels aux personnes de votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour les Voix Entreprise ou Plans d’appel d’Office 365. Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur les Plans d’appel d’Office 365, reportez-vous à la section [Quels sont les Plans d’appel dans Office 365 ?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) et [L’appel de Plans pour Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge en tant qu’Agents file d’attente un appel. 
  
- Vous ne pouvez attribuer d’appel payant et numéros de téléphone du service gratuit que vous avez obtenu dans la **Skype pour le centre d’administration Business** ou transférés à partir d’un autre fournisseur de service pour les files d’attente des appels système téléphonique. Pour obtenir et utiliser les numéros de service gratuit, vous devez configurer les crédits de Communications.
    
    > [!NOTE]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des files d'attente. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés. 
  
- Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :
    
  - Client de bureau Skype Entreprise 2016 (versions 32 et 64 bits)
    
  - Client de bureau Lync 2013 (versions 32 et 64 bits)
    
  - Tous les modèles de téléphone IP pris en charge par Skype Entreprise Online. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Skype Mac pour Client d’entreprise (version 16.8.196 ou version ultérieure) 
    
  - Android Skype pour Client d’entreprise (version 6.16.0.9 ou version ultérieure)
    
  - iPhone Skype pour Client d’entreprise (version 6.16.0 ou version ultérieure)
    
  - iPad Skype pour Client d’entreprise (version 6.16.0 ou version ultérieure)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Étape 2 : obtention ou transfert de numéros de service gratuits ou payants

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. Après avoir obtenu le numéro payant ou les numéros de téléphone de service gratuit, ils seront afficheront dans **Skype pour le centre d’administration de Business** > **vocale** > **les numéros de téléphone**et la volonté de **type nombre** répertorié comme **Service - numéro gratuit **. Pour obtenir vos numéros de service, voir [numéros de téléphone de service de mise en route pour Skype pour les entreprises et les équipes de Microsoft](getting-service-phone-numbers.md) ou si vous souhaitez de transfert et le numéro de service existant, consultez le [transfert vers Office 365, les numéros de téléphone](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous résidez hors des États-Unis, vous ne pouvez pas utiliser le Skype pour Business admin center pour obtenir les numéros de service. Aller à [Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.
  
## <a name="step-3---create-a-new-call-queue"></a>Étape 3 : création d'une file d'attente d'appels

Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Files d'attente d'appels**, puis cliquez sur **Ajouter nouveau**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Définissez le nom d'affichage de la file d'attente, un numéro de téléphone et un domaine (le cas échéant).

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Numéro 1](../images/sfbcallout1.png)<br/>
**Nom** Entrez un nom d'affichage descriptif pour la file d'attente d'appels. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.<br/> Ce nom sera affiché dans la notification de l'appel entrant.
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Numéro de téléphone** Sélectionnez un numéro de service gratuit ou payant pour la file d'attente d'appels. Cette option est facultative. <br/> Si aucun numéro n'est répertorié, vous devrez obtenir des numéros de service avant de créer cette file d'attente. Pour obtenir vos numéros de service, voir [numéros de téléphone de service de mise en route pour Skype pour les entreprises et les équipes de Microsoft](getting-service-phone-numbers.md)
***
![Numéro 3](../images/sfbcallout3.png)<br/>**Domaine** S'il est disponible, sélectionnez le domaine Office 365 que vous souhaitez utiliser. Ce champ sera uniquement disponible si vous disposez de plusieurs domaine utilisés avec Office 365. Si c'est le cas, vous devez choisir le nom de domaine dans la liste.<br/> Par exemple, le domaine peut se présenter comme suit :  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d'accueil et la musique lue pendant la mise en attente

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>Le **message d'accueil** est facultatif. C’est le message d’accueil qui est lu pour les personnes qui appellent dans le nombre de file d’attente d’appel. <br/> Vous pouvez télécharger un fichier audio (.wma, .mp3 ou .wav formats).
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Contenir de la musique sur** Vous pouvez utiliser la valeur par défaut de musique en attente fourni avec la file d’attente d’appel, ou vous pouvez télécharger un fichier audio .wav, mp3 ou .wma formats à utiliser comme votre musique en attente. 
   

### <a name="select-the-call-distribution-method"></a>Sélectionnez la méthode de distribution d’appel

![Affiche des options de méthode de distribution de l’appel](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Appelez la méthode de distribution** Vous pouvez choisir soit **standard** ou **série** pour la méthode de distribution file d’attente de votre appel. Toutes les files d’attente de l’appel de nouveaux et existants a surveillance du routage sélectionné par défaut. Pour utiliser la série de routage, vous devez choisir explicitement l’option routage **série** dans l’interface utilisateur et des applets de commande. <br/><br/> Lorsque l’itinéraire série est sélectionnée et que la file d’attente d’appel est enregistré, les appels à partir de la file d’attente sonnera vos agents un par un, à partir du début de la liste de l’agent. Si un agent fait disparaître ou ne récupère pas d’un appel, l’appel sonnera l’agent suivant dans la liste et va essayer de tous les agents un par un jusqu'à ce qu’elle est récupérée ou délai d’attente dans la file d’attente.  <br/><br/>  **Remarque :** Série de routage ignore les agents qui sont **en mode hors connexion**, ont défini de leur présence sur **ne pas déranger**ou qui ont **choisi** de recevoir des appels à partir de cette file d’attente.  
   
### <a name="select-an-agent-opt-out-option"></a>Sélectionnez un agent opt out

![Case à cocher indique que l’agent se désabonner](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**L’agent Opt out** Vous pouvez choisir d’autoriser les agents de file d’attente d’appel à refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **l’Option Refuser l’Agent**.  <br/> L’activation de cette option permet à tous les agents dans cette file d’attente pour démarrer ou arrêter la réception d’appel à partir de cette file d’attente de l’appel à seront. Vous pouvez révoquer le privilège d’annulations de l’agent à tout moment en désactivant la case à cocher, à l’origine des agents deviennent automatiquement sélectionné pour cette file d’attente à nouveau (le paramètre par défaut pour tous les agents).  <br/><br/> Pour accéder à l’option d’annulation d’abonnement, les agents peuvent effectuez les opérations suivantes :
 1. Ouvrez **Options** dans leur bureau Skype pour client d’entreprise. 
 2. Dans l’onglet **Transfert d’appel** , cliquez sur le lien **Modifier les paramètres en ligne** .
 3. Sur la page de paramètres utilisateur, cliquez sur **Appeler les files d’attente**, puis désactivez les cases à cocher pour les files d’attente pour lesquelles ils souhaitent se désabonner.
 
    > [!NOTE] 
    > Agents à l’aide de Mac, mobile, ou les clients Lync 2013 ou hybride voix utilisateurs hébergés sur site à l’aide de Skype pour serveur d’entreprise 2015, peut atteindre [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder aux opt out.
   
### <a name="add-call-agents-to-a-call-queue"></a>Ajouter des téléopérateurs à une file d'attente d'appels

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/>Agents d’appel (50 maximum) peuvent être :
*    Un utilisateur en ligne avec une licence de **Système téléphonique** et activée avec un Plan d’appel ou de Voix Entreprise. <br/><br/> **Remarque :**  Pour rediriger les appels aux personnes de votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour les Voix Entreprise ou un Plan d’appel. Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Utilisateurs en ligne avec un avec une licence de **Système téléphonique** et un appel de Plan qui sont ajoutés à un groupe d’Office 365, une liste de Distribution à extension messagerie ou un groupe de sécurité. Jusqu'à 30 minutes peuvent être nécessaires pour qu'un nouvel agent ajouté à une liste de distribution ou à un groupe de sécurité commence à recevoir des appels depuis une file d'attente. Un groupe de sécurité ou liste de distribution nouvellement créée peut prendre jusqu'à 48 heures deviennent disponibles pour être utilisés avec des files d’attente de l’appel. Nouvellement créé Office 365 groupes sont disponibles presque immédiatement. <br/> 

    > [!NOTE] 
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Définir la taille maximale de la file d'attente et la durée maximale d'attente

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/>**Nombre d'appels maximal dans la file d'attente** Utilisez cette valeur pour définir le nombre d'appels maximal qu'il peut y avoir simultanément dans la file d'attente. La valeur par défaut est de 50, mais elle peut varier de 0 à 200. Lorsque cette limite est atteinte, l’appel sera traité de façon que vous avez défini sur le paramètre **lorsque le nombre maximal d’appels est atteinte** ci-dessous.
***
![Numéro 2](../images/sfbcallout2.png)<br/><br/>**Lorsque le nombre maximal d’appels est atteinte.** Lorsque la file d’attente de l’appel atteint sa taille maximale (la valeur en utilisant le paramètre **Maximum appelle dans la file d’attente** ), vous pouvez choisir ce qui se passe à un nouvel appel entrant.
*    **Déconnexion avec signal Occupé** L'appel sera déconnecté.
*    **Transférer cet appel** Lorsque vous choisissez cette option, vous aurez ces options :
     *    **Personne dans votre entreprise** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour les Voix Entreprise ou disposer d’un Plan d’appel. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/> <br/>Pour en savoir plus sur les licences requises pour la messagerie vocale, reportez-vous à la section [configurer la messagerie vocale du système téléphonique](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 
     
        > [!Note]
        > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>
     
     *    **Appelez la file d’attente** Vous devez avoir créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente d’appel.
     *    **Standard automatique** Vous devez avoir créé une surveillance automatique, mais une fois que vous le faites, vous pouvez sélectionner cette surveillance automatique. Consultez [configurer une surveillance automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
***
![Numéro 3](../images/sfbcallout3.png)<br/><br/>**Durée d'attente d'un appel dans la file d'attente** Vous pouvez également décider de la durée maximale pendant laquelle un appel peut être mis en attente avant d'expirer ou d'être redirigé. La destination de redirection est basée sur la définition du paramètre **Lorsqu'un appel expire**. Le délai peut être défini entre 0 et 45 minutes.  <br/><br/> La valeur de délai d’attente peut être définie en secondes, à intervalles de 15 secondes. Cela vous permet de manipuler le flux d’appel avec une granularité plus fine. Par exemple, vous pouvez spécifier que tous les appels qui ne sont pas traités par un agent dans les 30 secondes passent à un Standard automatique de recherche répertoire. 

***
![Numéro 4](../images/sfbcallout4.png)<br/><br/>**Lorsqu'un appel expire** Lorsque l'appel atteint la limite définie par le paramètre **Durée d'attente d'un appel dans la file d'attente**, vous pouvez choisir le traitement ultérieur de l'appel en question :
*    **Déconnecter** L'appel sera déconnecté.
*    **Transférer cet appel** Lorsque vous choisissez cette option, vous aurez ces options :
     *    **Personne dans votre entreprise** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour les Voix Entreprise ou ont des Plans d’appel. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définir cette personne pour que leurs appels transférés directement vers la messagerie vocale. </br><br/>  Pour en savoir plus sur les licences requises pour la messagerie vocale, reportez-vous à la section [configurer la messagerie vocale du système téléphonique](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 

        > [!Note]
        > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>

     *    **Appelez la file d’attente** Vous devez avoir créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente d’appel.
     *    **Standard automatique** Vous devez avoir créé une surveillance automatique, mais une fois que vous le faites, vous pouvez sélectionner cette surveillance automatique. Consultez [configurer une surveillance automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modification de l’ID de l’utilisateur appelant pour être le numéro de téléphone d’une file d’attente appel

Vous pouvez protéger l’identité d’un utilisateur en modifiant à la place de leur ID de l’appelant pour les appels sortants d’une file d’attente de l’appel en créant une stratégie à l’aide de l’applet de commande **New-CallingLineIdentity** .
  
Pour ce faire, exécutez la commande :
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquer la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** . Pour ce faire, exécutez la commande :
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d’informations sur la façon de modifier les paramètres d’ID de l’appelant dans votre organisation [ici](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des files d'attente.
  
### <a name="call-queue-cmdlets"></a>Applets de commande de file d'attente d'appels

Voici les applets de commande requis pour gérer une file d'attente d'appels.
  
- [Nouvelle-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Ensemble-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Supprimer-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

## <a name="feedback"></a>Commentaires ?
Pour fournir des commentaires sur le produit ou pour nous faire savoir comment nous faisons, consultez [Skype pour les commentaires de l’entreprise](https://www.skypefeedback.com).