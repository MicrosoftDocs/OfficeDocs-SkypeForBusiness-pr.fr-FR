---
title: Configuration des conférences rendez-vous dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer l’appel de conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: f6d724f522ac264699a3bf7a3fb63749f7da0c05
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server-2015"></a>Configuration des conférences rendez-vous dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer l’appel de conférence dans Skype pour Business Server 2015.
  
Après avoir créé une topologie qui inclut la charge de conférence et des conférences à distance sélectionnée, vous devez exécuter des étapes supplémentaires pour configurer les conférences à distance. Avant de lire cette rubrique, veillez à ce que vous avez lu le [Plan pour les conférences à distance dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [matérielle et logicielle requise pour les conférences dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)et le diagramme de flux [déploiement et liste de vérification pour les conférences à distance](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing). 
  
Pour configurer la conférence rendez-vous, vous devez effectuer les tâches suivantes :
  
- [Configure dial plans](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configure dial-in conferencing regions](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configure dial-in access numbers](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configure conferencing policies](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
De plus, vous pouvez effectuer les tâches facultatives suivantes. Pour plus d’informations sur ces tâches facultatives, consultez [gérer à distance conférence dans Skype pour Business Server 2015](../../manage/conferencing/dial-in-conferencing.md).
  
- Gestion des stratégies de code confidentiel pour les conférences rendez-vous
    
- Gestion du mappage des clés des commandes DTMF
    
- Création d’un annuaire de conférences
    
- Gestion des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence
    
- Test des paramètres de conférence rendez-vous
    
- Envoi d’un message électronique de bienvenue aux utilisateurs rendez-vous
    
## <a name="configure-dial-plans"></a>Configurer des plans de numérotation
<a name="BKMK_ConfigureDialPlans"> </a>

Lorsque vous déployez la conférence rendez-vous, vous devez créer ou modifier un ou plusieurs plans de routage des numéros de téléphone d’accès entrant. Vous devez également vous assurer que chaque plan de numérotation contienne au moins une règle de normalisation--une règle qui convertit des extensions téléphoniques en numéros de téléphone complète au format E.164. 
  
Les utilisateurs de conférences rendez-vous participent à des conférences en tant qu’utilisateurs d’entreprise authentifiés en entrant leur code confidentiel et leur numéro de téléphone. Vous avez besoin d’une règle de normalisation pour convertir les numéros de poste en numéros de téléphone complets afin que les utilisateurs puissent être authentifiés lorsqu’ils saisissent simplement un numéro de poste.
  
Pour configurer des plans de numérotation pour la conférence rendez-vous :
  
- Que vous déployiez ou non Voix Entreprise, modifiez le plan de numérotation global pour ajouter une région de conférence rendez-vous et veillez à ce qu’une règle de normalisation convertisse avec précision vos numéros d’accès. Pour obtenir des instructions détaillées, reportez-vous à la section [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Si vous n’avez pas déployé Voix Entreprise, créez des plans de numérotation pour vos numéros d’accès aux conférences rendez-vous. Veillez à inclure une région de conférence rendez-vous. Pour obtenir des instructions détaillées, reportez-vous à la section [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Si vous avez déployé Voix Entreprise, modifiez, si nécessaire, les plans de numérotation de Voix Entreprise pour inclure des régions et utilisez les règles de normalisation appropriées pour les numéros d’accès entrant. Vous pouvez également créer des plans de numérotation dédiés, utilisés exclusivement pour les numéros d’accès entrant. Pour obtenir des instructions détaillées, reportez-vous à la section [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
Pour plus d’informations sur la création de règles de normalisation, consultez [créer ou modifier une règle de normalisation dans Skype pour 2015 de Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).
  
## <a name="configure-dial-in-conferencing-regions"></a>Configuration des régions de conférence rendez-vous
<a name="BKMK_ConfigureDialInRegions"> </a>

Lorsque vous créez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. La région de conférence rendez-vous associe des numéros d’accès aux conférences rendez-vous au plan de numérotation approprié. Quand vous créez le numéro d’accès à la conférence rendez-vous, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés. 
  
Comme il est important de spécifier une région pour tous les plans de numérotation, nous vous recommandons de vérifier que tous les plans de numérotation sont associés à des régions de conférence. 
  
Utilisez l’applet de commande **Get-CsDialPlan** pour vérifier qu’une région est configurée pour tous les plans de numérotation de conférence rendez-vous. Si ce n’est pas le cas, vous pouvez utiliser l’applet de commande **Set-CsDialPlan** pour configurer la région. Vous pouvez également utiliser Skype pour le panneau de configuration de Business Server pour mettre à jour la zone de dans des plans de numérotation existant. Pour plus d’informations sur l’utilisation de Skype pour le panneau de configuration de Business Server, consultez [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Pour vérifier que la région est correctement configurée dans les plans de numérotation

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   Exemple :
    
   ```
   Get-CsDialPlan
   ```

   Dans cet exemple, tous les plans de numérotation configurés pour votre organisation sont renvoyés.
    
4. Vérifiez les plans de numérotation renvoyés pour identifier ceux ne comportant pas la région de conférence rendez-vous. 
    
Pour plus d’informations, consultez [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>Pour définir la propriété de région d’un plan de numérotation

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Pour tous les plans de numérotation ne comportant pas de région de conférence rendez-vous, exécutez :
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Exemple :
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   Dans cet exemple, le plan de numérotation dont l’identité est Redmond est modifié afin de définir la propriété DialinConferencingRegion sur « US West Coast ». 
    
Pour plus d’informations, voir [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).
  
## <a name="configure-dial-in-access-numbers"></a>Configurer les numéros d’accès entrant
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences. Ces numéros s’affichent dans les invitations à une réunion et sur la page web des paramètres de configuration des conférences rendez-vous.
  
Avant de créer des numéros d’accès aux conférences rendez-vous, vous devez planifier vos régions de conférences rendez-vous puis configurer les plans de numérotation correspondants. Pour plus d’informations sur les zones, reportez-vous à [planification pour les conférences à distance dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md). Pour plus d’informations sur la configuration des plans pour les conférences à distance d’appel, consultez [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
> [!NOTE]
> Vous ne pouvez pas utiliser un nouveau numéro d’accès pour la conférence rendez-vous tant que la réplication AD DS de ce numéro n’est pas terminée. La réplication peut durer plusieurs heures. 
  
> [!NOTE]
> Une fois que vous avez créé les numéros d’accès aux conférences rendez-vous, vous pouvez modifier le nom complet des objets contact Active Directory pour permettre aux utilisateurs d’identifier plus facilement le numéro d’accès approprié. Pour modifier le nom d’affichage, utilisez l’applet de commande [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) . Vous ne devez pas modifier manuellement les objets Active Directory.
  
### <a name="to-create-a-dial-in-access-number"></a>Pour créer un numéro d’accès entrant

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.
    
4. Dans la page **Numéro d’accès entrant**, effectuez l’une des opérations suivantes :
    
   - Cliquez sur **Nouveau** pour ouvrir **Nouveau numéro d’accès entrant**.
    
   - Cliquez sur l’un des numéros d’accès entrant dans la liste, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
    > [!NOTE]
    > Utiliser le champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès entrant peut ne pas produire les résultats que vous attendez. Par conséquent, triez la liste selon la colonne qui vous intéresse pour identifier le numéro d’accès entrant que vous voulez afficher ou modifier. 
  
5. Dans **Numéro affiché**, tapez le numéro de téléphone que les utilisateurs du réseau téléphonique commuté (RTC) composent pour rejoindre une conférence. Ce numéro est affiché dans les invitations aux réunions et dans la page web des paramètres des conférences rendez-vous.
    
6. In **Nom d’affichage**, tapez la description du numéro d’accès entrant. Il s’agit de celui qui est associé au numéro d’accès à distance dans Skype pour les résultats de la recherche. Ce nom est affiché dans le client lorsqu’un utilisateur appelle le numéro d’accès. 
    
7. Dans **URI de ligne**, tapez le numéro E.164 du numéro d’accès entrant au format d’URI TEL, avec le symbole + avant le numéro et sans espace. Par exemple, tel :+14255550200.
    
    > [!NOTE]
    > Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. 
  
8. Dans **URI SIP**, procédez comme suit :
    
   - Dans la zone de texte, tapez un URI SIP (Session Initiation Protocol) unique pour ce numéro d’accès à une conférence rendez-vous. Cet URI SIP est affiché dans divers emplacements, y compris, mais non limité, pour appeler des messages de notification et les versions antérieures de clients Lync.
    
    > [!NOTE]
    > Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. Il n’est pas possible de modifier l’URI SIP une fois que le numéro d’accès est créé. Le seul moyen de modifier l’URI SIP est de supprimer et de recréer le numéro d’accès. 
  
   - Dans la zone de liste déroulante, cliquez sur le domaine de l’application de la surveillance du conférence qui prend en charge ce nombre d’accès à distance.
    
9. Dans **Pool**, cliquez sur le pool qui exécute l’instance d’Intendant Conférence qui prend en charge ce numéro d’accès entrant.
    
    > [!NOTE]
    > Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’applet de commande [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) ou supprimer et recréer le numéro d’accès.
  
10. Dans **Langue principale**, cliquez sur la langue des invites pour ce numéro d’accès entrant. 
    
    La langue principale est la langue que l’Intendant Conférence utilise pour répondre aux appels. Les langues prises en charge sont affichées avec chaque numéro de téléphone d’accès dans la page web des paramètres des conférences rendez-vous.
    
11. (Facultatif) Dans **Langues secondaires (quatre au maximum)**, cliquez sur **Ajouter**, sélectionnez les langues supplémentaires que vous souhaitez prendre en charge pour les personnes qui appellent ce numéro d’accès entrant, puis cliquez sur **OK**. 
    
    Vous pouvez sélectionner jusqu’à quatre langues secondaires pour chaque numéro d’accès entrant. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de la conférence à laquelle ils souhaitent participer.
    
12. Pour ajouter une région pour le numéro d’accès à distance, dans **les régions associés**, cliquez sur **Ajouter**, cliquez sur une ou plusieurs zones qui sont associés à des plans de numérotation de ce numéro d’accès à distance, puis cliquez sur **OK**.
    
13. Pour supprimer une région du numéro d’accès entrant, sous **Régions associées**, cliquez sur la région que vous souhaitez supprimer, puis cliquez sur **Supprimer**.
    
14. Cliquez sur **Valider**.
    
## <a name="configure-conferencing-policies"></a>Configuration des stratégies de conférence
<a name="BKMK_ConfigureConferencingPolicies"> </a>

Une stratégie de conférence est un paramètre de compte d’utilisateur qui spécifie les modalités de la conférence pour les participants. Vous pouvez créer des stratégies de conférence avec une étendue de site ou d’utilisateur. Les paramètres de stratégie de conférence englobent de nombreux aspects de la planification de la conférence et de la participation. Plusieurs paramètres de stratégies de conférence prennent en charge la conférence rendez-vous pour les participants. Lorsque vous configurez une conférence rendez-vous, vous devez vérifier que ces champs sont correctement définis pour votre organisation, et vous devez les modifier uniquement en cas de nécessité. 
  
Pour plus d’informations sur la configuration des stratégies de la conférence, voir [Gérer les stratégies de conférence dans Skype pour Business Server 2015](../../manage/conferencing/conferencing-policies.md).
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Assign a Line URI to a user account
<a name="BKMK_AssignaLineURI"> </a>

Les utilisateurs d’appels entrants doivent entrer un numéro de téléphone ou de poste, ainsi qu’un code confidentiel pour participer à des conférences en qualité d’utilisateurs authentifiés. La téléphonie **Ligne URI** spécifié sur Skype pour les comptes d’utilisateurs de serveur d’entreprise est requise pour l’authentification.
  
La procédure décrite dans cette rubrique explique comment affecter un **URI de ligne** pour un compte utilisateur unique. Si vous devez attribuer un **URI de ligne** à plusieurs comptes utilisateur, vous pouvez créer un script à l’aide de l’applet de commande **Set-CsUser**. Pour plus d’informations sur l’utilisation d’un exemple de script pour attribuer des **URI de ligne** à plusieurs comptes d’utilisateurs, voir [Attribuer des URI de ligne à plusieurs utilisateurs](https://go.microsoft.com/fwlink/p/?linkId=196945).
  
1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-UserAdministrator** ou **CsAdministrator**.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans le champ de recherche, tapez le nom de l’utilisateur à configurer pour une conférence rendez-vous ou cliquez sur **Ajouter un filtre** pour spécifier les champs de la recherche, puis cliquez sur **Rechercher**.
    
5. Double-cliquez sur le nom utilisateur pour ouvrir la boîte de dialogue **Modifier l’utilisateur Skype Entreprise Server**.
    
6. Sous **Téléphonie**, dans le champ **URI de ligne**, tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).
    
    > [!NOTE]
    > Vous pouvez spécifier un **URI de ligne** uniquement si l’option **Téléphonie** est définie sur **De PC à PC uniquement**, **Voix Entreprise**, **Contrôle d’appel distant** ou **Contrôle d’appel distant uniquement**. 
  
7. Cliquez sur **Valider**.
    

