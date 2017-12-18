---
title: "Créer une file d'attente des appels système téléphonique"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061

description: "Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. "
---

# Créer une file d'attente des appels système téléphonique

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Appel système téléphonique files d'attente contiennent des messages d'accueil qui sont utilisés lorsque quelqu'un appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de recherche pour l'agent appel disponible suivante gérer l'appel pendant les personnes qui appel écoutent musicale. Vous pouvez créer une ou plusieurs files d'attente d'appel pour votre organisation.
  
Files d'attente des appels téléphoniques système peuvent fournir :
  
- Un message d'accueil pour l'organisation
    
- Une attente musicale
    
- Redirection des appels à appeler agents dans les groupes de sécurité et de listes de distribution à extension messagerie.
    
- Définir des paramètres pour taille maximale appel file d'attente, délai d'expiration et options de gestion des appels.
    
Lorsqu'une personne appelle un numéro de téléphone défini vers le haut d'une file d'attente de l'appel, ils entendront un message d'accueil premier (si un a été configurée), puis ils est placé dans la file d'attente et attendez que l'agent appel disponible suivante. La personne appelant entendront musique pendant qu'ils sont en attente en attente, et les appels seront proposés aux agents appel de la manière  *First In, First Out*  (FIFO).
  
Tous les appels en attente dans la file d'attente seront distribués à l'aide d'un standard routage mode ou en série routage (disponible pour les clients Preview uniquement) :
  
- Avec le routage standard, le premier appel dans la file d'attente sonne tous les agents en même temps.
    
- Avec le routage en série, le premier appel dans la file d'attente sonne tous les agents appel un par un (disponible pour les clients Preview uniquement).
    
-     > [!NOTE]
    > Appel agents qui sont **en mode hors connexion**, ont défini ses informations de présence sur **ne pas déranger** ou ont choisi de ne pas la file d'attente d'appel ne sera pas appelés.
  
- Une seule notification d'appel entrant (pour l'appel en tête de file) sera envoyée aux téléopérateurs à la fois.
    
- Lorsqu'un téléopérateur accepte l'appel, le prochain appel entrant dans la file d'attente sonnera pour les autres téléopérateurs.
    
## Étape 1 : prise en main

Avant de commencer à utiliser les files d'attente d'appels, il est impératif de noter les points suivants :
  
- Votre organisation doit avoir (au minimum) une licence entreprise E3 plus **Système téléphonique** ou une licence entreprise E5. Le nombre de licences utilisateur **Système téléphonique** affectés affecte le nombre de numéros de service sont disponibles pour être utilisés pour les files d'attente d'appel. Le nombre de files d'attente d'appel que vous pouvez avoir est dépend du nombre de licences **Système téléphonique** et de **Conférence Audio** qui sont affectées dans votre organisation. Pour en savoir plus sur les licences, accédez[Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Pour rediriger les appels aux personnes de votre organisation qui sont en ligne, ils doivent disposer d'une licence **Système téléphonique** et être activés pour voix entreprise ou Office 365 appel d'offre. Voir[Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple exécuter :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur Office 365 appel d'offre, voir [Quelle est l'appel d'offre dans Office 365 ?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) et[Plans d'appel pour Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Les utilisateurs hébergés en local à l'aide de Lync Server 2010 ne sont pas pris en charge en tant qu'Agents file d'attente un appel. 
  
- Vous pouvez uniquement affecter payants et des numéros de téléphone du service gratuit que vous avez dans **Skype centre d'administration Business** ou transféré à partir d'un autre fournisseur de services aux files d'attente des appels système téléphonique. Pour obtenir et utiliser des numéros de service gratuit, vous devez configurer les Communications crédits.
    
    > [!NOTE]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des files d'attente. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés. 
  
- Lorsque vous distribuez les appels entrants à partir d'une file d'attente des appels système téléphonique, ces clients sont pris en charge pour les appels agents :
    
  - Client de bureau Skype Entreprise 2016 (versions 32 et 64 bits)
    
  - Client de bureau Lync 2013 (versions 32 et 64 bits)
    
  - Tous les modèles de téléphone IP pris en charge pour Skype Entreprise Online. Reportez-vous à la page [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype entreprise (version 16.8.196 et versions ultérieures)
    
  - Android Skype entreprise (version 6.16.0.9 et versions ultérieures)
    
  - iPhone Skype entreprise (version 6.16.0 et versions ultérieures)
    
  - iPad Skype entreprise (version 6.16.0 et versions ultérieures)
    
## Étape 2 : obtention ou transfert de numéros de service gratuits ou payants

Avant de pouvoir créer et configurer vos files d'attente d'appel, vous devrez obtenir ou transférer votre numéro payant existant ou un service gratuit nombres. Une fois que vous obtenez le numéro payant ou gratuit service des numéros de téléphone, ils seront affichent dans **Skype centre d'administration entreprise** > **vocale** > **numéros de téléphone** et l'est de **type numérique** répertorié être répertoriée en tant que **Service - gratuit**. Pour obtenir vos numéros de service, voir les [Obtention des numéros de téléphone des services Skype Entreprise](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) ou si vous souhaitez transférer et numéro de service existant, voir[Transférer des numéros de téléphone vers Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype centre d'administration entreprise pour obtenir des numéros de service. Accédez [Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour apprendre à le faire à partir de l'extérieur des États-Unis.
  
## Étape 3 : création d'une file d'attente d'appels

Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Files d'attente d'appels**, puis cliquez sur **Ajouter nouveau**:
  
### Définissez le nom d'affichage de la file d'attente, un numéro de téléphone et un domaine (le cas échéant).

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Nom** Entrez un nom d'affichage descriptif pour la file d'attente d'appels. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris. <br/> Ce nom sera affiché dans la notification de l'appel entrant.  <br/> |
|**2** <br/> |**Numéro de téléphone** Sélectionnez un numéro payant service ou le numéro de téléphone gratuit pour la file d'attente d'appel. Cette étape est facultative. <br/> Si aucun numéro n'est répertorié, vous devrez obtenir des numéros de service avant de créer cette file d'attente. Pour obtenir vos numéros de service, reportez-vous à l'article [Obtention des numéros de téléphone des services Skype Entreprise](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) <br/> |
|**3** <br/> |**Domaine** S'il est disponible, sélectionnez le domaine Office 365 que vous souhaitez utiliser. Ce champ sera uniquement disponible si vous disposez de plusieurs domaine utilisés avec Office 365. Si c'est le cas, vous devez choisir le nom de domaine dans la liste. <br/> Par exemple, le domaine peut se présenter comme suit :  _contoso.com or redmond.contoso.com_ <br/> |
   
### Définir le message d'accueil et la musique lue pendant la mise en attente

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Formule d'appel** est facultative. Il s'agit de la carte de vœux qui est lu pour les personnes qui rejoignent le nombre de file d'attente d'appel. <br/> Vous pouvez télécharger un fichier audio (.wav, MP3 ou .wma formats).  <br/> |
|**2** <br/> |**Maintenez la touche musique sur** Vous pouvez utiliser la valeur par défaut musique en attente fournis avec la file d'attente d'appel, ou vous pouvez télécharger un fichier audio .wav, mp3 ou .wma formats à utiliser comme votre musicale personnalisé. <br/> |
   
### Sélectionnez la méthode de distribution appel (disponible pour les clients Preview uniquement)

![Shows the call distribution method options](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Appeler la méthode de distribution** Vous pouvez choisir **standard** ou **en série** pour votre méthode de distribution file d'attente d'appel. Toutes les files d'appel, existants et nouveaux aura routage standard sélectionné par défaut. Pour utiliser le routage en série, vous devez choisir explicitement l'option routage **en série** dans l'interface utilisateur et les applets de commande. <br/> Lorsque le routage en série est sélectionné et la file d'attente d'appel est enregistré, les appels à partir de la file d'attente sonne vos agents un par un, à partir du début de la liste des agents. Si un agent ferme ou ne récupère pas d'un appel, l'appel sonne l'agent suivant dans la liste et tentera de tous les agents un par un jusqu'à ce qu'il est sélectionné vers le haut ou expire attendre dans la file d'attente.  <br/> > [!NOTE]> Routage en série ignorent les agents qui sont **en mode hors connexion**, ont défini ses informations de présence sur **ne pas déranger** ou qui ont **choisi** de recevoir des appels à partir de cette file d'attente.          |
   
### Sélectionnez un agent désactiver cette fonctionnalité option (disponible pour les clients Preview uniquement)

![Shows the agent opt out check box](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Agent de désactiver cette fonctionnalité option** Vous pouvez choisir d'autoriser les agents de file d'attente d'appel cesser d'utiliser répondre aux appels une file d'attente spécifique en sélectionnant **L'Agent désactiver cette fonctionnalité option**.  <br/> Activer cette option permet à tous les agents dans cette file d'attente pour démarrer ou arrêter de recevoir des appels à partir de cette file d'attente d'appel en seront. Vous pouvez révoquer les privilèges annulations agent à tout moment en désactivant la case à cocher, à l'origine d'agents pour devenir automatiquement choisi de participer pour cette file d'attente à nouveau (paramètre par défaut pour tous les agents).  <br/> Pour accéder à l'option d'annulation, agents pouvant procédez comme suit :  <br/> 1. Ouvrez **Options** dans leur bureau Skype entreprise. <br/> 2. dans l'onglet **Transfert d'appel**, cliquez sur le lien **Modifier les paramètres en ligne** <br/> 3. dans la page de paramètres utilisateur, cliquez sur **Appel files d'attente** et puis désactivez les cases à cocher pour les files d'attente pour lesquelles ils souhaitent désactiver cette fonctionnalité. <br/> |
   
### Ajouter des téléopérateurs à une file d'attente d'appels

![Set up call queues.](../images/9c0c551b-218b-4268-9b73-c85000c99296.png)
  
|||
|:-----|:-----|
|**1** <br/> | Les téléopérateurs (50 maximum) peuvent être : <br/>  Un utilisateur en ligne avec une licence de **Système téléphonique** activé pour voix entreprise ou avec un Plan de l'appel. <br/> > [!NOTE]>  Pour rediriger les appels aux personnes de votre organisation qui sont en ligne, ils doivent disposer d'une licence **Système téléphonique** et être activés pour voix entreprise ou dispose d'un Plan d'appel. Voir[Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple exécuter :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`           Les utilisateurs en ligne avec un avec une licence **Système téléphonique** ou un appel de Plan qui sont ajoutés à une liste de Distribution ou un groupe de sécurité à extension messagerie. Il peut prendre jusqu'à 30 minutes pour un nouvel agent ajouté pour une liste de distribution ou un groupe de sécurité pour recevoir des appels à partir d'une file d'attente d'appel. Un groupe de sécurité ou liste de distribution nouvellement créé peut prendre jusqu'à 48 heures soit disponible pour être utilisé avec files d'attente d'appel. <br/> > [!NOTE]>  Groupes Office 365 (groupes moderne) ne peuvent pas être utilisés avec files d'attente d'appel.          > [!NOTE]>  Les utilisateurs hébergés en local à l'aide de Lync Server 2010 ne sont pas pris en charge.          |
   
### Définir la taille maximale de la file d'attente et la durée maximale d'attente

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
|||
|:-----|:-----|
|**1**|**Valeur maximale des appels dans la file d'attente** Utilisez cette option pour définir les appels maximales qui peuvent attendre dans la file d'attente en même temps. La valeur par défaut est achevée à 50, mais il peut être comprise entre 0 et 200.Lorsque la limite est atteinte, l'appel sera traité de la manière définie par le paramètre **Lorsque la limite maximale du nombre d'appels est atteinte** ci-après.|
|**2**|**Lorsque le nombre maximal d'appels est atteint.** Lorsque la file d'attente appel atteint sa taille maximale (en utilisant le paramètre **Maximum appelle dans la file d'attente** ), vous pouvez choisir qu'advient-il des nouveaux appels entrants. **Déconnexion avec signal Occupé** L'appel sera déconnecté. **Transférer cet appel** Lorsque vous choisissez cette option, vous devrez ces options : **Personne de votre société** Un utilisateur en ligne avec une licence **Système téléphonique** et être activé pour voix entreprise ou dispose d'un Plan de l'appel. Vous pouvez le configurer vers le haut pour la personne appelant peut être envoyée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne doit avoir leurs appels transférés directement vers la messagerie vocale.> [!NOTE]>  Les utilisateurs hébergés en local à l'aide de Lync Server 2010 ne sont pas pris en charge.          **Appeler file d'attente** Vous devez avoir déjà créé un autre file d'attente appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d'attente d'appel. **Standard automatique** Vous devez avoir déjà créé un standard automatique, mais une fois que vous le faites, vous pouvez sélectionner ce standard automatique. Voir[Configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md). |
|**3**|**Durée d'attente d'un appel dans la file d'attente** Vous pouvez également décider de la durée maximale pendant laquelle un appel peut être mis en attente avant d'expirer ou d'être redirigé. La destination de redirection est basée sur la définition du paramètre **Lorsqu'un appel expire**. Le délai peut être défini entre 0 et 45 minutes.> [!NOTE]> **Disponible pour les clients Preview uniquement :** La valeur du délai d'attente peut être définie en secondes, toutes les 15 secondes. Cela vous permet de manipuler le flux d'appels avec précise. Par exemple, vous pouvez spécifier que tous les appels qui ne sont pas traitées par un agent dans les 30 secondes atteindre un standard automatique de recherche de répertoire.          |
|**4**|**Lorsqu'un appel expire** Lorsque l'appel atteint la limite définie par le paramètre **Durée d'attente d'un appel dans la file d'attente**, vous pouvez choisir le traitement ultérieur de l'appel en question : **Déconnecter** L'appel sera déconnecté. **Transférer cet appel** Lorsque vous choisissez cette option, vous devrez ces options : **Personne de votre société** Un utilisateur en ligne avec une licence **Système téléphonique** et être activé pour voix entreprise ou que l'appel d'offre. Vous pouvez le configurer vers le haut pour la personne appelant peut être envoyée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne doit avoir leurs appels transférés directement vers la messagerie vocale.> [!NOTE]>  Les utilisateurs hébergés en local à l'aide de Lync Server 2010 ne sont pas pris en charge.          **Appeler file d'attente** Vous devez avoir déjà créé un autre file d'attente appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d'attente d'appel. **Standard automatique** Vous devez avoir déjà créé un standard automatique, mais une fois que vous le faites, vous pouvez sélectionner ce standard automatique. Voir[Configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md). |
   
## Modification des ID de l'appelant de l'utilisateur pour être numéro de téléphone d'un appel la file d'attente

Vous pouvez protéger identité d'un utilisateur en modifiant leur ID d'appelant pour les appels sortants à appel en attente à la place en créant une stratégie à l'aide de l'applet de commande **New-CallingLineIdentity**.
  
Pour ce faire, exécutez :
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquer la stratégie à l'utilisateur à l'aide de l'applet de commande **Grant-CallingLineIdentity**. Pour ce faire, exécutez :
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d'informations sur la façon de modifier les paramètres d'ID de l'appelant dans votre organisation [Comment utiliser un ID d'appelant dans votre organisation](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des files d'attente.
  
### Applets de commande de file d'attente d'appels

Voici les applets de commande requis pour gérer une file d'attente d'appels.
  
- [New-CsHuntgroup ](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup ](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup ](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup ](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### Informations supplémentaires sur PowerShell Windows

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

