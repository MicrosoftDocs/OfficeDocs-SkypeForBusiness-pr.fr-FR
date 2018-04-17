---
title: Préparation d’Active Directory pour Skype Entreprise Server 2015
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
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Summary: Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a1344bab451bd9c4b46a0147bd2ffb1190dbe900
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Préparation d’Active Directory pour Skype Entreprise Server 2015
 
**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype for Business Server works closely with Active Directory. You must prepare the Active Directory domain to work with Skype for Business Server. This process is accomplished in the Deployment Wizard and is only done once for the domain. Ceci est dû au fait que le processus crée des groupes et modifie le domaine et vous n’avez besoin d’effectuer cette opération qu’une seule fois. Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5 comme indiqué dans le diagramme. Preparing Active Directory is step 4 of 8. For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![schéma de vue d’ensemble](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Préparer Active Directory

Skype for Business Server 2015 is tightly integrated with Active Directory Domain Services (AD DS). Before Skype for Business Server 2015 can be installed for the first time, Active Directory must be prepared. The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server 2015 uses (AD DS) to track and communicate with all of the servers in a topology. Every server must be joined to the domain so that Skype for Business Server can work properly. 
  
> [!IMPORTANT]
> La procédure Préparer Active Directory ne doit être effectuée qu’une seule fois pour chaque domaine du déploiement. 
  
Regardez en vidéo les étapes pour **préparer Active Directory** :
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/272c856b-b3e0-4324-9635-42720c48b75a?autoplay=false]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Préparation d’Active Directory à partir de l’Assistant déploiement

1. Connectez-vous comme utilisateur avec des données d’identification d’administrateur de schéma pour le domaine Active Directory.
    
2. Open Skype for Business Server Deployment Wizard.
    
    > [!TIP]
    > If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step. For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Cliquez sur le lien **Préparer Active Directory**.
    
4. **Step 1: Prepare schema**
    
    a. Passez en revue les informations requises pour l’étape 1, qui sont accessibles par un clic sur la liste déroulante sous le titre de l’étape 1.
    
    b. Cliquez sur **Exécuter** dans l’étape 1 pour lancer l’assistant Préparer le schéma.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque déploiement. Cliquez alors sur **Suivant**.
    
    d. Une fois que le schéma a été préparé, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    e. Cliquez sur **Terminer** pour fermer l’assistant Préparer le schéma et revenez aux étapes de préparation d’Active Directory.
    
5. **Step 2: Verify replication of schema partition**
    
    a. Connectez-vous au contrôleur de domaine pour le domaine en question.
    
    b. Ouvrez **Modification ADSI** à partir du menu déroulant **Outils** dans **Gestionnaire de serveur**.
    
    c. Dans le menu **Action**, cliquez sur **Connexion**.
    
    d. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
    e. Sous le conteneur de schéma, recherchez **CN=ms-RTC-SIP-SchemaVersion**. Si cet objet existe et si la valeur de l’attribut **rangeUpper** est 1150 et si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès. Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.
    
6. **Step 3: Prepare current forest**
    
    a. Passez en revue les informations requises pour l’étape 3, qui sont accessibles par un clic sur la liste déroulante sous le titre de l’étape 3.
    
    b. Cliquez sur **Exécuter** dans l’étape 3 pour lancer l’assistant Préparer la forêt actuelle.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque déploiement. Cliquez alors sur **Suivant**.
    
    d. Précisez le domaine dans lequel les groupes universels seront créés. Si le serveur fait partie du domaine, vous pouvez choisir **Domaine local** et cliquer sur **Suivant**.
    
    e. Une fois que la forêt a été préparée, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    f. Cliquez sur **Terminer** pour fermer l’assistant Préparer la forêt actuelle et revenez aux étapes de préparation d’Active Directory.
    
    g. Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    h. Type the command Get-CsAdForest, and press **Enter**.
    
    i. If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.
    
     ![Vérification de la réplication de forêt.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Step 4: Verify replication of the global catalog**
    
    a. Sur un contrôleur de domaine (de préférence sur un site distant par rapport aux autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été effectuée, ouvrez **Utilisateurs et ordinateurs Active Directory**.
    
    b. Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.
    
    c. Cliquez sur le conteneur **Utilisateurs** dans le volet de gauche et recherchez le groupe universel **CsAdministrator** dans le volet de droite. Si CsAdministrator (parmi huit autres nouveaux groupes universels commençant par Cs) est présent, la réplication d’Active Directory a réussi.
    
    d. Si les groupes ne sont pas encore présents, vous pouvez forcer la réplication ou attendre 15 minutes, puis actualiser le volet de droite. Lorsque les groupes apparaissent, la réplication est terminée.
    
8. **Step 5: Prepare the current domain**
    
    a. Passez en revue les informations requises pour l’étape 5.
    
    b. Cliquez sur **Exécuter** dans l’étape 5 pour lancer l’assistant Préparer le domaine actuel.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque domaine du déploiement. Cliquez alors sur **Suivant**.
    
    d. Une fois que le domaine a été préparé, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    e. Cliquez sur **Terminer** pour fermer l’assistant Préparer le domaine actuel et revenez aux étapes de préparation d’Active Directory.
    
    These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start. Il peut notamment s’agir de n’importe quel objet Active Directory, tel qu’utilisateurs, objets de contact, groupes administratifs, ou tout autre objet. You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.
    
9. **Step 6: Verify replication in the domain**
    
    a. Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    b. Use the command Get-CsAdDomain to verify replication within the domain.
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > Si vous omettez le paramètre Domain, le domaine local est utilisé. 
  
    Exemple d’exécution de la commande pour le domaine contoso.local :
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > En utilisant le paramètre GlobalSettingsDomainController, vous pouvez indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (ce qui est caractéristique des déploiements de mise à niveau pour lesquels le paramètre global n’a pas migré vers le conteneur de configuration), vous devez définir un contrôleur de domaine dans la racine de votre forêt AD DS. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et indique un contrôleur de domaine dans Active Directory. 
  
    c. If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.
    
10. **Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**
    
    a. Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.
    
    b. Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez sur le conteneur **Utilisateurs**, cliquez avec le bouton droit sur CSAdministrator, puis choisissez **Propriétés**.
    
    c. Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.
    
    d. Sous l’onglet **Membres**, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.
    
    e. Sous l’onglet **Membres**, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.
    
    > [!CAUTION]
    > The Skype for Business Server Control Panel is a role-based access control tool. Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available. Il existe d’autres rôles disponibles conçus pour des fonctions spécifiques. For details on the roles available, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups. 
  
    > [!CAUTION]
    > To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment. 
  
11. Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.
    
12. Vérifiez la présence d’une coche verte à côté de **Préparer Active Directory** pour confirmer que vous avez réussi, comme indiqué dans la figure.
    
     ![Préparation d’Active Directory terminée.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

