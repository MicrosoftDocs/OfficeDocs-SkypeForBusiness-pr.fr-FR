---
title: Configurer la conférence d’accès dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer la conférence téléphonique dans Skype Entreprise Server.'
---

# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Configurer la conférence d’accès dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer la conférence d’accès dans Skype Entreprise Server.
  
Après avoir créé une topologie qui inclut la charge de travail de conférence et la conférence téléphonique sélectionnée, vous devez effectuer des étapes supplémentaires pour configurer la conférence d’accès. Avant de lire cette rubrique, assurez-vous d’avoir lu la rubrique [Plan for dial-in conferencing in Skype Entreprise Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype Entreprise Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), ainsi que l’exemple de flux de déploiement et la liste de contrôle pour les conférences d’accès[.](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing) 
  
Pour configurer la conférence téléphonique, vous devez effectuer les tâches suivantes :
  
- [Configurer des plans de numérotation](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configurer des régions de conférences téléphoniques](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configurer les numéros d’accès entrant](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configurer des stratégies de conférence](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Affecter un URI de ligne à un compte d’utilisateur](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
En outre, vous pouvez effectuer les tâches facultatives suivantes. Pour plus d’informations sur ces tâches facultatives, voir Gérer les conférences [rendez-vous dans Skype Entreprise Server](../../manage/conferencing/dial-in-conferencing.md).
  
- Gérer les stratégies de code confidentiel pour les conférences téléphoniques
    
- Gérer le mappage de touches pour les commandes DTMF
    
- Créer des annuaires des conférences
    
- Gérer les annonces de rejoindre et de quitter une conférence
    
- Tester les paramètres de conférences téléphoniques
    
- Envoyer un message de bienvenue aux utilisateurs d’appels
    
## <a name="configure-dial-plans"></a>Configurer des plans de numérotation
<a name="BKMK_ConfigureDialPlans"> </a>

Lorsque vous déployez la conférence rendez-vous, vous devez créer ou modifier un ou plusieurs plans de routage des numéros de téléphone d’accès entrant. Vous devez également vous assurer que chaque plan de numérotation contient au moins une règle de normalisation , c’est-à-dire une règle qui convertit les numéros de poste en numéros de téléphone complets au format E.164. 
  
Les utilisateurs de conférences rendez-vous participent à des conférences en tant qu’utilisateurs d’entreprise authentifiés en entrant leur code confidentiel et leur numéro de téléphone. Vous avez besoin d’une règle de normalisation pour convertir des postes en numéros de téléphone complets afin que les utilisateurs puissent être authentifiés lorsqu’ils saisissent simplement un numéro de poste.
  
Pour configurer des plans de numérotation pour les conférences téléphoniques :
  
- Que vous déployiez ou non Voix Entreprise, modifiez le plan de numérotation global pour ajouter une région de conférence rendez-vous et pour vous assurer qu’une règle de normalisation convertit précisément vos numéros d’accès aux conférences rendez-vous. Pour obtenir des instructions détaillées, voir [Créer ou modifier un plan](../../deploy/deploy-enterprise-voice/dial-plans.md) de numérotation dans Skype Entreprise Server.
    
- Si vous n’avez pas déployé Voix Entreprise, créez des plans de numérotation pour vos numéros d’accès aux conférences téléphoniques. Veillez à inclure une région de conférence rendez-vous. Pour obtenir des instructions détaillées, voir [Créer ou modifier un plan](../../deploy/deploy-enterprise-voice/dial-plans.md) de numérotation dans Skype Entreprise Server.
    
- Si vous avez déployé Voix Entreprise, modifiez Voix Entreprise plans de numérotation si nécessaire pour inclure des régions et utilisez les règles de normalisation appropriées pour les numéros d’accès aux appels. Vous pouvez également créer des plans de numérotation dédiés, utilisés exclusivement pour les numéros d’accès entrant. Pour obtenir des instructions détaillées, voir [Créer ou modifier un plan](../../deploy/deploy-enterprise-voice/dial-plans.md) de numérotation dans Skype Entreprise Server.
    
Pour plus d’informations sur la création de règles de normalisation, voir Créer ou modifier une règle de [normalisation dans Skype Entreprise](../../deploy/deploy-enterprise-voice/normalization-rules.md).
  
## <a name="configure-dial-in-conferencing-regions"></a>Configurer des régions de conférences téléphoniques
<a name="BKMK_ConfigureDialInRegions"> </a>

Lorsque vous établissez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. La région de conférence téléphonique associe les numéros d’accès aux conférences téléphoniques au plan de numérotation approprié. Lorsque vous créez le numéro d’accès, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés. 
  
Comme il est important de spécifier une région pour tous les plans de numérotation, nous vous recommandons de vérifier que tous les plans de numérotation ont des régions de conférence. 
  
Pour vérifier si la région est définie pour tous les plans de numérotation de conférences téléphoniques, utilisez l **';** Si ce n’est pas le cas, vous pouvez utiliser l’applet de commande **Set-CsDialPlan** pour configurer la région. Vous pouvez également utiliser Skype Entreprise Server de contrôle d’accès pour mettre à jour la région dans les plans de numérotation existants. Pour plus d’informations sur l Skype Entreprise Server du Panneau de Skype Entreprise Server, voir Créer ou modifier un plan de numérotation [dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Pour vérifier que la région est correctement configurée dans les plans de numérotation

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Exécutez la commande suivante à l’invite de commandes :
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   Par exemple :
    
   ```powershell
   Get-CsDialPlan
   ```

   Dans cet exemple, tous les plans de numérotation configurés pour votre organisation sont retournés.
    
4. Vérifiez les plans de numérotation retournés pour identifier ceux ne comportant pas la région de conférence rendez-vous. 
    
Pour plus d’informations, [voir Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps).
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>Pour définir la propriété de région d’un plan de numérotation

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Pour tous les plans de numérotation ne comportant pas de région de conférence rendez-vous, exécutez :
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Par exemple :
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   Dans cet exemple, le plan de numérotation dont l’identité est Redmond est modifié afin de définir la propriété DialinConferencingRegion sur « US West Coast ». 
    
Pour plus d’informations, [voir Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps).
  
## <a name="configure-dial-in-access-numbers"></a>Configurer les numéros d’accès entrant
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences. Ces numéros apparaissent dans les invitations à une réunion et sur la page Web des paramètres de configuration des conférences rendez-vous.
  
Avant de créer des numéros d’accès aux conférences rendez-vous, vous devez planifier vos régions de conférences rendez-vous puis configurer les plans de numérotation correspondants. Pour plus d’informations sur les régions, voir [Plan for dial-in conferencing in Skype Entreprise Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md). Pour plus d’informations sur la configuration des plans de numérotation pour la conférence rendez-vous, voir Créer ou modifier un [plan de numérotation dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
> [!NOTE]
> Vous ne pouvez pas utiliser un nouveau numéro d’accès pour la conférence rendez-vous tant que la réplication AD DS de ce numéro n’est pas terminée. La réplication peut durer plusieurs heures. 
  
> [!NOTE]
> Une fois que vous avez créé les numéros d’accès aux conférences rendez-vous, vous pouvez modifier le nom complet des objets contact Active Directory pour permettre aux utilisateurs d’identifier plus facilement le numéro d’accès approprié. Pour modifier le nom complet, utilisez l’cmdlet [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) . Vous ne devez pas modifier manuellement les objets Active Directory.
  
### <a name="to-create-a-dial-in-access-number"></a>Pour créer un numéro d’accès à la connexion

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.
    
4. Dans la page **Numéro d’accès à la** connexion, faites l’une des choses suivantes :
    
   - Cliquez **sur Nouveau** pour **ouvrir le nouveau numéro d’accès à la connexion**.
    
   - Cliquez sur l’un des numéros d’accès à la connexion dans la liste, cliquez sur **Modifier, puis** sur **Afficher les détails**.
    
     > [!NOTE]
     > L’utilisation du champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès à la connexion risque de ne pas produire les résultats que vous attendez. Au lieu de cela, tiez la liste par colonne d’intérêt pour identifier le numéro d’accès à la connexion que vous souhaitez afficher ou modifier. 
  
5. Dans **le numéro d’affichage**, tapez le numéro de téléphone composé par les utilisateurs du réseau téléphonique commuté (PSTN) pour participer à une conférence. Ce numéro s’affiche dans les invitations aux réunions et sur la page web Paramètres conférence rendez-vous.
    
6. Dans **le nom d’affichage**, tapez une description pour le numéro d’accès à la connexion. Il s’agit du nom associé au numéro d’accès à la connexion dans les Skype Entreprise de recherche. Ce nom s’affiche dans le client lorsqu’un utilisateur appelle le numéro d’accès. 
    
7. Dans **l’URI** de ligne, tapez le numéro E.164 du numéro d’accès à la numérotation au format URI TEL, en incluant le symbole + avant le numéro et en excluant les espaces. Par exemple, `tel:+14255550200`.
    
    > [!NOTE]
    > Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès aux conférences téléphoniques. 
  
8. Dans **l’URI SIP**, faites les choses suivantes :
    
   - Dans la zone de texte, tapez un URI SIP unique pour ce numéro d’accès de conférence. Cet URI SIP s’affiche à différents emplacements, y compris, mais sans s’y limiter, les messages de notification d’appel et les versions précédentes des clients Lync.
    
     > [!NOTE]
     > Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès de conférence. L’URI SIP ne peut pas être modifié après la création du numéro d’accès. La seule façon de modifier l’URI SIP consiste à supprimer et recréer le numéro d’accès. 
  
   - Dans la zone de liste liste, cliquez sur le domaine du application Assistant de conférence qui prend en charge ce numéro d’accès à la connexion.
    
9. Dans **pool**, cliquez sur le pool qui exécute l’instance de Assistant de conférence qui prend en charge ce numéro d’accès à la connexion.
    
    > [!NOTE]
    > Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’cmdlet [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) ou supprimer et recréer le numéro d’accès.
  
10. Dans **la langue principale**, cliquez sur la langue dans laquelle les invites sont lées pour ce numéro d’accès à la connexion. 
    
    La langue principale est la langue que le Assistant de conférence utilise pour répondre à l’appel. Les langues prise en charge sont affichées avec chaque numéro de téléphone d’accès sur la page web conférence Paramètres conférences.
    
11. (Facultatif) Dans **les langues secondaires (** quatre au maximum), cliquez sur **Ajouter,** sélectionnez une ou plusieurs langues supplémentaires que vous souhaitez prendre en charge pour les appelants de ce numéro d’accès à la conférence, puis cliquez sur **OK**. 
    
    Vous pouvez choisir jusqu’à quatre langues secondaires pour chaque numéro d’accès à la connexion. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de conférence lorsqu’ils participent à une conférence.
    
12. Pour ajouter une région pour le numéro d’accès à la **connexion, sous** Régions associées, cliquez sur **Ajouter, cliquez** sur une ou plusieurs régions associées aux plans de numérotation pour ce numéro d’accès, puis cliquez sur **OK**.
    
13. Pour supprimer une région du numéro d’accès à la connexion, sous **Régions** associées, cliquez sur la région à supprimer, puis cliquez sur **Supprimer**.
    
14. Cliquez sur **Valider**.
    
## <a name="configure-conferencing-policies"></a>Configurer des stratégies de conférence
<a name="BKMK_ConfigureConferencingPolicies"> </a>

Une stratégie de conférence est un paramètre de compte d’utilisateur qui spécifie les modalités de la conférence pour les participants. Vous pouvez créer des stratégies de conférence avec une étendue de site ou d’utilisateur. Les paramètres de stratégie de conférence englobent de nombreux aspects de la planification de la conférence et de la participation. Plusieurs paramètres de stratégies de conférence prennent en charge la conférence rendez-vous pour les participants. Lorsque vous configurez une conférence rendez-vous, vous devez vérifier que ces champs sont correctement définis pour votre organisation, et vous devez les modifier uniquement en cas de nécessité. 
  
Pour plus d’informations sur la configuration des stratégies de conférence, voir Gérer les stratégies de conférence [dans Skype Entreprise Server](../../manage/conferencing/conferencing-policies.md).
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Affecter un URI de ligne à un compte d’utilisateur
<a name="BKMK_AssignaLineURI"> </a>

Les utilisateurs d’appels entrants doivent entrer un numéro de téléphone ou de poste, ainsi qu’un code confidentiel pour participer à des conférences en qualité d’utilisateurs authentifiés. **L’URI de ligne** téléphonique spécifié sur Skype Entreprise Server comptes d’utilisateurs est requis pour l’authentification.
  
La procédure décrite dans cette rubrique explique comment affecter un **URI de ligne** pour un seul compte d’utilisateur. Si vous devez affecter un **URI de ligne** à plusieurs comptes d’utilisateur, vous pouvez créer un script qui utilise l’applet de commande **Set-CsUser**. Pour plus d’informations sur l’utilisation d’un exemple de script pour attribuer un **URI** de ligne à plusieurs comptes d’utilisateurs, voir [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).
  
1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-UserAdministrator** ou **CsAdministrator**.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans le champ de recherche, tapez le nom de l’utilisateur à configurer pour une conférence rendez-vous ou cliquez sur **Ajouter un filtre** pour spécifier les champs de la recherche, puis cliquez sur **Rechercher**.
    
5. Double-cliquez sur le nom d’utilisateur pour ouvrir la **boîte de dialogue Modifier Skype Entreprise Server’utilisateur**.
    
6. Sous **Téléphonie**, dans le champ **URI de ligne**, tapez un numéro de téléphone normalisé unique (par exemple, tel:+14255550200).
    
    > [!NOTE]
    >  Vous pouvez spécifier **l’URI** de ligne uniquement si la téléphonie est définie sur **PC à PC** uniquement, **Voix Entreprise****, Contrôle** d’appel distant ou Contrôle d’appel **distant uniquement**. 
  
7. Cliquez sur **Valider**.
