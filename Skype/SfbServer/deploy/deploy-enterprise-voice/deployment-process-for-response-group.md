---
title: Procédure de déploiement de Response Group dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processus de déploiement et les étapes pour Response Group dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: e84d8507ca64228a1bf6773110b5122d25286636
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-response-group-in-skype-for-business-2015"></a>Procédure de déploiement de Response Group dans Skype Entreprise 2015
 
Processus de déploiement et les étapes pour Response Group dans Skype pour Business Server Enterprise Voice.
  
Response Group est une fonctionnalité de voix entreprise qui achemine et files d’attente des appels entrants aux groupes de personnes, appelés agents, par exemple un support technique ou d’un service clientèle.
  
Response Group requiert les composants sont installés et activés automatiquement sur le serveur frontal ou Standard Edition server lors du déploiement d’Enterprise Voice. Pour rendre Response Group accessible aux utilisateurs, vous devez configurer des flux de travail files d’attente, puis groupes d’agents. En outre, un administrateur de groupe de réponse peuvent déléguer la configuration d’un flux de travail existant à un gestionnaire Response Group, qui peut ensuite modifier et reconfigurer le flux de travail et ses groupes d’agents associés et les files d’attente.
  
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
> **(1)** l’objet de Services de domaine Active Directory un utilisateur doit être un membre du groupe de sécurité Active Directory spécifié répertorié. Un administrateur ou autres délégué membre du groupe Active Directory avec les autorisations appropriées pour ajouter des utilisateurs à un groupe de sécurité (par exemple, administrateur, opérateurs de compte) doit ajouter un objet utilisateur au groupe de sécurité répertoriés ou au groupe de l’utilisateur pour être en mesure de exécuter les fonctions répertoriées. **(2)** uniquement pour les flux de travail qui vous a attribué la CsResponseGroupAdministrator la CsResponseGroupManager. **(3)** Gestionnaire A Response Group peut affecter un autre membre de CsResponseGroupManager à un flux de travail qui gère le déjà le gestionnaire en cours. **(4)** CsViewOnlyAdministrator peut exécuter uniquement verbe « Obtenir » des applets de commande.
  
## <a name="response-group-configuration-prerequisites"></a>Conditions préalables de Configuration Response Group

Response Group requiert les composants suivants :
  
- service d’application
    
- application Response Group
    
- Modules linguistiques
    
- Magasin de fichiers (pour conserver les fichiers audio)
    
- Services Web (inclut l’outil de Configuration Response Group et la console des agents connexion et déconnexion)
    
Tous ces composants sont installés par défaut lors du déploiement d’Enterprise Voice.
  
Vous devrez peut-être effectuer les tâches suivantes avant de configurer Response Group :
  
- Activer les utilisateurs pour Lync Server 2013 et Enterprise Voice.
    
- Modification d’un fichier de configuration pour la conformité aux normes FIPS (Federal Information Processing Standard)
    
- Modification du classement de base de données pour prendre en charge les caractères Yi, Meng et Zang pour les noms des files d’attente et des groupes d’agents
    
### <a name="enabling-users"></a>Activation des utilisateurs

La première étape de configuration de Response Group consiste à créer des groupes d’agents. Avant de pouvoir créer un groupe d’agents, vous devez activer les utilisateurs qui seront les agents pour le groupe de réponses pour Skype pour les entreprises et Enterprise Voice. Activation des utilisateurs pour Skype pour les entreprises est généralement une étape dans le serveur Enterprise Edition server ou un déploiement Standard Edition server. Pour plus d’informations sur l’activation des utilisateurs pour Skype pour les entreprises, voir [Activer ou désactiver des utilisateurs pour Lync Server 2013 Preview](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). Activation des utilisateurs pour Enterprise Voice est généralement une étape du déploiement d’Enterprise Voice. Pour plus d’informations, voir [Activer les utilisateurs pour Enterprise Voice dans Skype pour Business Server 2015](enable-users-for-enterprise-voice.md). 
  
### <a name="complying-with-fips-requirements"></a>Conformité aux normes FIPS

Cette section ne vous concerne que si votre organisation doit se conformer aux normes FIPS (Federal Information Processing Standard).
  
Pour respecter les normes FIPS, vous devez modifier le fichier d’application Web.config afin d’utiliser un autre algorithme de chiffrement une fois les services web installés. Vous devez préciser qu’ASP.NET utilise l’algorithme de chiffrement triple 3DES (Triple Data Encryption Standard) pour traiter les données d’état d’affichage. Pour l’application Response Group, cette exigence s’applique à l’outil de Configuration Response Group et de la console de connexion et déconnexion des agents. Pour plus d’informations sur cette exigence, consultez l’article 911722 de la Base de connaissances Microsoft, « vous receviez un message d’erreur lorsque vous accédez aux pages Web ASP.NET dont l’état d’affichage activé après la mise à niveau à partir d’ASP.NET 1.1 vers ASP.NET 2.0, « à [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183).
  
Pour modifier le fichier Web.config, procédez comme suit :
  
1. Dans un éditeur de texte, comme Bloc-Notes, ouvrez le fichier d’application Web.config.
    
2. Dans le fichier Web.config, localisez la `<system.web>` section.
    
3. Ajoutez le code suivant `<machineKey>` section dans le `<system.web>` section :
    
   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Enregistrez le fichier Web.config.
    
5. Redémarrez le service Internet Information Services (IIS) en exécutant la commande suivante à une invite de commandes : 
    
   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Prise en charge des caractères Yi, Meng et Zang

Cette section ne vous concerne que si votre organisation doit prendre en charge les caractères Yi, Meng ou Zang.
  
> [!NOTE]
> Pour plus d’informations sur les caractères Yi, Meng et Zang et pourquoi ils peuvent être importantes pour votre déploiement, consultez les informations sur les jeux de caractères GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223). 
  
Pour assurer une prise en charge des caractères Yi, Meng ou Zang, vous devez modifier le classement de la base de données Rgsconfig. Modifiez le classement de la colonne **Nom** des tableaux ci-dessous dans chaque base de données Rgsconfig :
  
- dbo. AgentGroups
    
- dbo. BusinessHours
    
- dbo. HolidaySets
    
- dbo. Files d’attente
    
- dbo. Flux de travail
    
Pour SQL Server 2008 R2 et SQL Server 2012, utilisez la Latin_General_100 (accents) classement. Si vous utilisez ce classement, certains noms d’objet ne dépendent pas des minuscules/majuscules.
  
Vous pouvez modifier le classement à l’aide de Microsoft SQL Server Management Studio. Pour plus d’informations sur l’utilisation de cet outil, voir [« à l’aide de SQL Server Management Studio »](https://go.microsoft.com/fwlink/p/?linkId=196184). Pour modifier le classement, procédez comme suit :
  
1. Assurez-vous que SQL Server Management Studio est configuré de manière à autoriser les modifications nécessaires à la recréation des tables. Pour plus d’informations, voir [« Enregistrer (non autorisé) boîte de dialogue «](https://go.microsoft.com/fwlink/p/?linkId=196186). Pour plus d’informations sur la définition d’un classement de colonne, voir à [« Comment : ensemble de classement de la colonne (outils de base de données Visual) «](https://go.microsoft.com/fwlink/p/?linkId=196185).
    
2. À l’aide de Microsoft SQL Server Management Studio, connectez-vous à la base de données Rgsconfig.
    
3. Recherchez la table à modifier dans la base de données Rgsconfig, cliquez avec le bouton droit sur la table, puis cliquez sur **Conception**. 
    
4. Modifiez le classement de la colonne **Nom** et enregistrez la table.
    
## <a name="response-group-deployment-steps"></a>Procédure de déploiement de Response Group

**Processus de déploiement de Response Group**

|**Phase**|**Étapes**|**Autorisations**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Permettre aux utilisateurs de Skype pour les entreprises et pour Enterprise Voice  <br/> |Permettre aux utilisateurs qui seront agents pour Skype pour les entreprises et Enterprise Voice. Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents. En règle générale, les utilisateurs sont activés pour Skype pour les entreprises au cours de l’édition entreprise ou d’un déploiement Standard Edition server. Les utilisateurs sont activés pour Enterprise Voice lors du déploiement d’Enterprise Voice.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Activer ou désactiver des utilisateurs pour Lync Server 2013 Preview](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Activer les utilisateurs pour Enterprise Voice sur Skype pour Business Server 2015](enable-users-for-enterprise-voice.md) <br/> |
|Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail  <br/> |1. Utilisez le Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell pour effectuer les opérations suivantes :  <br/> a. Créez et configurez des groupes d’agents.  <br/> b. Créez et configurez des files d’attente.  <br/> 2. vous pouvez également utiliser Skype pour Business Server Management Shell pour créer une réponse prédéfinie groupe heures et jours fériés.  <br/> 3. Utilisez l’outil de Configuration pour Response Group ou de Skype pour Business Server Management Shell pour créer des workflows (groupes de recherche ou flux d’appels réponse vocale interactive), y compris une réponse personnalisée groupe heures et jours fériés.  <br/> Vous pouvez accéder l’outil de Configuration Response Group via Skype pour le panneau de configuration serveur Business.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Créer des groupes d’agents Response Group](http://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Créer des files d’attente Response Group](http://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(Facultatif) Groupe de réponse de définir les heures d’ouverture Skype pour Business 2015](optional-define-response-group-business-hours.md) <br/> [(Facultatif) Définir Response Group de congés dans Skype pour Business 2015](optional-define-response-group-holiday-sets.md) <br/> [Concevoir et créer des flux de travail de groupe de réponse dans Skype pour Business 2015](designing-and-creating-response-group-workflows.md) <br/> |
|(Facultatif) Personnaliser les paramètres au niveau de l’application  <br/> |Utilisez Skype pour Business Server Management Shell pour personnaliser la configuration d’attente musicale par défaut, le fichier audio du attente musicale par défaut, la période de grâce de rappel de l’agent et la configuration de contexte d’appel.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gestion des paramètres de Response Group au niveau de l’application dans Skype pour Business 2015](managing-application-level-response-group-settings.md) <br/> |
|(Facultatif) Déléguer la gestion des groupes Response Group  <br/> |Affecter des utilisateurs au rôle CsResponseGroupManager pour déléguer la configuration des groupes de réponses. Responsables de groupe de réponse peuvent alors configurer les groupes Response Group qui leur.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planification de contrôle d’accès basé sur un rôle](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Vérifier votre déploiement Response Group  <br/> |Testez la réponse aux appels des flux de travail de votre groupe de recherche et de votre système de réponse vocale interactive pour vérifier que la configuration fonctionne comme prévu.  <br/> |-  <br/> |-  <br/> |
   
## <a name="overview-of-workflow-creation-scenarios"></a>Vue d’ensemble des scénarios de création de flux de travail

Lorsque vous créez des flux de travail, deux scénarios sont possibles :
  
- **L’Administrateur crée et configure le flux de travail** : le membre du rôle CsResponseGroupAdministrator (ou équivalent) crée et active le flux de travail, ainsi que tous les éléments qu’il contient, comme les groupes d’agents, les files d’attente, les congés et les heures ouvrées, la musique d’attente, etc.
    
- **L’administrateur crée le flux de travail et le responsable configure les options** : le membre du rôle CsResponseGroupAdministrator (ou équivalent) définit l’URI SIP (Session Initiation Protocol) principal et le nom complet, affecte des membres du rôle CsResponseGroupManager, sélectionne une file d’attente et active le flux de travail. Le membre du rôle CsResponseGroupManager peut ensuite ouvrir une session et modifier la configuration du flux de travail en créant des groupes d’agents. Il affecte également le groupe à la file d’attente, configure le numéro de téléphone, les congés et les heures ouvrées, la musique d’attente, etc.
    
    > [!NOTE]
    > Lorsque vous voulez créer un flux de travail géré, vous devez créer le flux travail en tant que flux de travail actif. Une fois que vous avez enregistré un flux de travail géré et actif, vous pouvez le modifier et le désactiver. 
  

