---
title: Procédure de déploiement de Response Group dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processus de déploiement et les étapes pour le groupe de réponse dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: ca390f19b98921f6c8d7fa2a02c8e5065e605a94
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-response-group-in-skype-for-business-2015"></a>Procédure de déploiement de Response Group dans Skype Entreprise 2015
 
Processus de déploiement et les étapes pour le groupe de réponse dans Skype pour Business Server Voix Entreprise.
  
Groupe de réponse est une fonctionnalité de Voix Entreprise qui achemine et files d’attente d’appels entrants à des groupes d’utilisateurs, appelés agents, tel qu’un service d’assistance technique ou d’un service d’assistance client.
  
Les composants requis du groupe de réponse sont installés et activés automatiquement sur le serveur frontal ou Standard Edition serveur lors du déploiement de Voix Entreprise. Pour rendre le groupe de réponse disponible aux utilisateurs, vous devez configurer des flux de travail files d’attente, puis les groupes d’agents. En outre, un administrateur de groupe de réponse peut déléguer la configuration d’un workflow existant à un gestionnaire de groupe réponse, qui peut alors modifier et reconfigurer le flux de travail et ses groupes d’agents associés et les files d’attente.
  
Pour configurer les groupes Response Group, vous devez être membre d’au moins l’un des rôles d’administrateur suivants :
  
|**Groupe de sécurité Active Directory (1)** <br/> |Création d’un flux de travail  <br/> |Affectation d’un responsable  <br/> |Création/Affectation des agents, des files d’attente  <br/> |Création/Gestion des congés et des heures d’ouverture  <br/> |Activation/Désactivation d’un flux de travail  <br/> |Configuration d’un flux de travail (réponse vocale interactive ou groupe de recherche)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |
   
> [!NOTE]
> **(1)** l’objet de Services de domaine Active Directory un utilisateur doit être membre du groupe de sécurité Active Directory spécifié énuméré. Un administrateur ou autre membre de groupe Active Directory délégué disposant des autorisations appropriées pour ajouter des utilisateurs à un groupe de sécurité (par exemple, administrateur, opérateurs de compte) doit ajouter un objet utilisateur au groupe de sécurité répertoriés ou au groupe de l’utilisateur pour pouvoir exécuter les fonctions répertoriées. **(2)** uniquement pour les workflows qui vous a attribué la CsResponseGroupAdministrator la CsResponseGroupManager. **(3)** responsable de groupe de réponse A peut affecter un autre membre de CsResponseGroupManager à un flux de travail qui gère déjà les le gestionnaire en cours. **(4)** CsViewOnlyAdministrator ne peut exécuter que des cmdlets « Get » de verbe.
  
## <a name="response-group-configuration-prerequisites"></a>Groupe de réponse Configuration préalable

Groupe de réponse nécessite les composants suivants :
  
- service d’application
    
- application Response Group
    
- Modules linguistiques
    
- Magasin de fichiers (pour conserver les fichiers audio)
    
- Services Web (inclut l’outil de Configuration de groupe de réponse et console de connexion et de déconnexion des agents)
    
Tous ces composants sont installés par défaut lors du déploiement de Voix Entreprise.
  
Vous devrez peut-être effectuer les tâches suivantes avant de configurer le groupe de réponse :
  
- Permettre aux utilisateurs de Lync Server 2013 et Voix Entreprise.
    
- Modification d’un fichier de configuration pour la conformité aux normes FIPS (Federal Information Processing Standard)
    
- Modification du classement de base de données pour prendre en charge les caractères Yi, Meng et Zang pour les noms des files d’attente et des groupes d’agents
    
### <a name="enabling-users"></a>Activation des utilisateurs

La première étape de la configuration de groupe de réponse consiste à créer des groupes de l’agent. Avant de pouvoir créer un groupe d’agents, vous devez activer les utilisateurs qui seront les agents pour groupe de réponse Skype pour les entreprises et les Voix Entreprise. Activation des utilisateurs pour Skype pour entreprise est généralement une étape dans le déploiement de Standard Edition server ou le serveur Enterprise Edition. Pour plus d’informations sur l’activation des utilisateurs pour Skype pour les entreprises, voir [Activer ou désactiver des utilisateurs pour Lync Server 2013 Preview](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). Activation des utilisateurs pour les Voix Entreprise est en général une étape dans le déploiement de Voix Entreprise. Pour plus d’informations, reportez-vous à la section [permettre aux utilisateurs de Voix Entreprise dans Skype pour Business Server 2015](enable-users-for-enterprise-voice.md). 
  
### <a name="complying-with-fips-requirements"></a>Conformité aux normes FIPS

Cette section ne vous concerne que si votre organisation doit se conformer aux normes FIPS (Federal Information Processing Standard).
  
Pour respecter les normes FIPS, vous devez modifier le fichier d’application Web.config afin d’utiliser un autre algorithme de chiffrement une fois les services web installés. Vous devez préciser qu’ASP.NET utilise l’algorithme de chiffrement triple 3DES (Triple Data Encryption Standard) pour traiter les données d’état d’affichage. Pour l’application de groupe de réponse, cette exigence s’applique à l’outil de Configuration de groupe de réponse et la console de connexion et de déconnexion de l’agent. Pour plus d’informations sur cette exigence, consultez l’article 911722 de la Base de connaissances Microsoft, « peut s’afficher un message d’erreur lorsque vous accédez aux pages Web ASP.NET qui ont activé après l’installation d’ASP.NET 1.1 vers ASP.NET 2.0, état d’affichage » à [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183).
  
Pour modifier le fichier Web.config, procédez comme suit :
  
1. Dans un éditeur de texte, comme Bloc-Notes, ouvrez le fichier d’application Web.config.
    
2. Dans le fichier Web.config, localisez la `<system.web>` section.
    
3. Ajoutez le code suivant `<machineKey>` section dans le `<system.web>` section :
    
   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Enregistrez le fichier Web.config.
    
5. Redémarrez le service Internet Information Services (IIS) en exécutant la commande suivante à une invite de commande : 
    
   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Prise en charge des caractères Yi, Meng et Zang

Cette section ne vous concerne que si votre organisation doit prendre en charge les caractères Yi, Meng ou Zang.
  
> [!NOTE]
> Pour plus d’informations sur les caractères Yi Meng et Zang et pourquoi ils peuvent être importantes à votre déploiement, consultez les informations sur les jeux de caractères GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223). 
  
Pour assurer une prise en charge des caractères Yi, Meng ou Zang, vous devez modifier le classement de la base de données Rgsconfig. Modifiez le classement de la colonne **Nom** des tableaux ci-dessous dans chaque base de données Rgsconfig :
  
- dbo. AgentGroups
    
- dbo. BusinessHours
    
- dbo. HolidaySets
    
- dbo. Files d’attente
    
- dbo. Flux de travail
    
Pour SQL Server 2008 R2 et SQL Server 2012, utiliser le Latin_General_100 (accents) classement. Si vous utilisez ce classement, certains noms d’objet ne dépendent pas des minuscules/majuscules.
  
Vous pouvez modifier le classement à l’aide de Microsoft SQL Server Management Studio. Pour plus d’informations sur l’utilisation de cet outil, reportez-vous à la section [« à l’aide de SQL Server Management Studio »](https://go.microsoft.com/fwlink/p/?linkId=196184). Pour modifier le classement, procédez comme suit :
  
1. Assurez-vous que SQL Server Management Studio est configuré de manière à autoriser les modifications nécessaires à la recréation des tables. Pour plus d’informations, reportez-vous à la section [« Enregistrer (non autorisé) boîte de dialogue «](https://go.microsoft.com/fwlink/p/?linkId=196186). Pour plus d’informations sur la définition d’un classement de colonne, reportez-vous à [« Comment : jeu de classement de la colonne (Visual Database Tools) »](https://go.microsoft.com/fwlink/p/?linkId=196185).
    
2. À l’aide de Microsoft SQL Server Management Studio, connectez-vous à la base de données Rgsconfig.
    
3. Recherchez la table à modifier dans la base de données Rgsconfig, cliquez avec le bouton droit sur la table, puis cliquez sur **Conception**. 
    
4. Modifiez le classement de la colonne **Nom** et enregistrez la table.
    
## <a name="response-group-deployment-steps"></a>Procédure de déploiement de Response Group

**Processus de déploiement de groupe de réponse**

|**Phase de**|**Étapes**|**Autorisations**|**Documentation sur le déploiement**|
|:-----|:-----|:-----|:-----|
|Permettre aux utilisateurs de Skype pour l’entreprise et de Voix Entreprise  <br/> |Permettre aux utilisateurs qui seront les agents pour Skype pour les entreprises et les Voix Entreprise. Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents. En général, les utilisateurs sont activés pour Skype pour les entreprises au cours de l’édition entreprise ou d’un déploiement de serveur Standard Edition. Les utilisateurs sont activés pour Voix Entreprise lors du déploiement de Voix Entreprise.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Activer ou désactiver des utilisateurs pour Lync Server 2013 Preview](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Permettre aux utilisateurs de Voix Entreprise dans Skype pour Business Server 2015](enable-users-for-enterprise-voice.md) <br/> |
|Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail  <br/> |1. Utilisez le Skype pour panneau de commande du serveur Business ou Skype pour Business Server Management Shell pour effectuer le des opérations suivantes :  <br/> a. Créez et configurez des groupes d’agents.  <br/> b. Créez et configurez des files d’attente.  <br/> 2. vous pouvez également utiliser Skype pour Business Server Management Shell pour créer une réponse prédéfinie groupe les heures et les jours fériés.  <br/> 3. Utilisez l’outil de Configuration de groupe de réponse ou un Skype pour Business Server Management Shell pour créer des workflows (groupes de recherche ou flux d’appel vocale interactive (IVR) de réponse), y compris une réponse personnalisée groupe les heures et les jours fériés.  <br/> Vous pouvez accéder de l’outil de Configuration de groupe de réponse via Skype pour le panneau de configuration de Business Server.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Créer des groupes d’Agent groupe de réponse](http://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Créer des files d’attente du groupe de réponse](http://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(Facultatif) Groupe de réponse de définir les heures de bureau dans Skype pour entreprise 2015](optional-define-response-group-business-hours.md) <br/> [(Facultatif) Jour férié de définir Response Group définit dans Skype pour entreprise 2015](optional-define-response-group-holiday-sets.md) <br/> [Conception et création de flux de travail de groupe réponse dans Skype pour entreprise 2015](designing-and-creating-response-group-workflows.md) <br/> |
|(Facultatif) Personnaliser les paramètres au niveau de l’application  <br/> |Utiliser Skype pour Business Server Management Shell pour personnaliser la configuration de la musique en attente par défaut, le fichier audio de musique en attente par défaut, la période de grâce de retour d’appel de l’agent et la configuration de contexte d’appel.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gestion des paramètres de groupe de réponse au niveau de l’application dans Skype pour entreprise 2015](managing-application-level-response-group-settings.md) <br/> |
|(Facultatif) Déléguer la gestion des groupes Response Group  <br/> |Affecter des utilisateurs au rôle CsResponseGroupManager pour déléguer la configuration des groupes de réponse. Gestionnaires de groupe de réponse peuvent alors configurer les groupes de réponse qui leur sont affectées.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planification pour le contrôle d’accès basé sur les rôles](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Vérifier votre déploiement Response Group  <br/> |Testez la réponse aux appels des flux de travail de votre groupe de recherche et de votre système de réponse vocale interactive pour vérifier que la configuration fonctionne comme prévu.  <br/> |-  <br/> |-  <br/> |
   
## <a name="overview-of-workflow-creation-scenarios"></a>Vue d’ensemble des scénarios de création de flux de travail

Lorsque vous créez des flux de travail, deux scénarios sont possibles :
  
- **L’Administrateur crée et configure le flux de travail** : le membre du rôle CsResponseGroupAdministrator (ou équivalent) crée et active le flux de travail, ainsi que tous les éléments qu’il contient, comme les groupes d’agents, les files d’attente, les congés et les heures ouvrées, la musique d’attente, etc.
    
- **L’administrateur crée le flux de travail et le responsable configure les options** : le membre du rôle CsResponseGroupAdministrator (ou équivalent) définit l’URI SIP (Session Initiation Protocol) principal et le nom complet, affecte des membres du rôle CsResponseGroupManager, sélectionne une file d’attente et active le flux de travail. Le membre du rôle CsResponseGroupManager peut ensuite ouvrir une session et modifier la configuration du flux de travail en créant des groupes d’agents. Il affecte également le groupe à la file d’attente, configure le numéro de téléphone, les congés et les heures ouvrées, la musique d’attente, etc.
    
    > [!NOTE]
    > Lorsque vous voulez créer un flux de travail géré, vous devez créer le flux travail en tant que flux de travail actif. Une fois que vous avez enregistré un flux de travail géré et actif, vous pouvez le modifier et le désactiver. 
  

