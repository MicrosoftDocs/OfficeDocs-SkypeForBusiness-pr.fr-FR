---
title: Préparation d’Active Directory pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Résumé : Découvrez comment préparer votre domaine Active Directory pour une installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018175"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Préparation d’Active Directory pour Skype entreprise Server
 
**Résumé :** Découvrez comment préparer votre domaine Active Directory pour une installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype entreprise Server fonctionne en étroite collaboration avec Active Directory. Vous devez préparer le domaine Active Directory pour qu’il fonctionne avec Skype entreprise Server. Ce processus est effectué dans l’Assistant Déploiement et n’est effectué qu’une seule fois pour le domaine. Cela est dû au fait que le processus crée des groupes et modifie le domaine, et vous ne devez effectuer cette opération qu’une seule fois. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. La préparation d’Active Directory est l’étape 4 sur 8. Pour plus d’informations sur la planification d’Active Directory, voir [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagramme de vue d’ensemble](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Préparer Active Directory

Skype entreprise Server est étroitement intégré aux services de domaine Active Directory (AD DS). Avant de pouvoir installer Skype entreprise Server pour la première fois, vous devez préparer Active Directory. Section de l’Assistant Déploiement intitulée **Prepare Active Directory** prepare the Active Directory Environment for use with Skype for Business Server.
  
> [!NOTE]
> Skype entreprise Server utilise (AD DS) pour effectuer le suivi et communiquer avec tous les serveurs d’une topologie. La plupart de ces serveurs doivent être joints au domaine afin que Skype entreprise Server puisse fonctionner correctement. N’oubliez pas que les serveurs tels que le serveur Edge et le proxy inverse ne doivent pas être joints au domaine.
  
> [!IMPORTANT]
> La procédure prepare Active Directory ne doit être exécutée qu’une seule fois pour chaque domaine dans le déploiement. 
  
Regardez les étapes vidéo de **préparation d’Active Directory**:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Préparation d’Active Directory à partir de l’Assistant Déploiement

1. Ouvrez une session en tant qu’utilisateur avec des informations d’identification d’administrateur de schéma pour le domaine Active Directory.
    
2. Ouvrez l’Assistant Déploiement de Skype entreprise Server.
    
    > [!TIP]
    > Si vous souhaitez consulter les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté, dans le répertoire utilisateurs de l’utilisateur AD DS qui a exécuté l’étape. Par exemple, si l’utilisateur a ouvert une session en tant qu’administrateur de domaine dans le domaine contoso. local, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Cliquez sur le lien **Préparer Active Directory** .
    
4. **Étape 1 : préparer le schéma**
    
    a. Consultez les informations sur les éléments prérequis pour l’étape 1 accessible en cliquant sur la liste déroulante sous le titre étape 1.
    
    b. Cliquez sur **exécuter** à l’étape 1 pour lancer l’Assistant Préparation du schéma.
    
    c. Notez que la procédure ne doit être exécutée qu’une seule fois pour chaque déploiement, puis cliquez sur **suivant**.
    
    d. Une fois que le schéma a été préparé, vous pouvez afficher le journal en cliquant sur **afficher le journal**. 
    
    e. Cliquez sur **Terminer** pour fermer l’Assistant préparer le schéma et revenir aux étapes préparer Active Directory.
    
5. **Étape 2 : vérifier la réplication de la partition de schéma**
    
    a. Ouvrez une session sur le contrôleur de domaine pour le domaine.
    
    b. Ouvrez **ADSI Edit** dans le menu déroulant **Outils** dans le **Gestionnaire de serveur**.
    
    c. Dans le menu **Action**, cliquez sur **Connexion à**.
    
    d. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
    e. Sous le conteneur de schéma, recherchez **CN = MS-RTC-SIP-SchemaVersion**. Si cet objet existe et que la valeur de l’attribut **rangeUpper** est de 1150 et que la valeur de l’attribut **rangeLower** est 3, le schéma a été mis à jour et répliqué avec succès. Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas spécifiées, le schéma n’a pas été modifié ou n’a pas été répliqué.
    
6. **Étape 3 : préparer la forêt actuelle**
    
    a. Consultez les informations sur les conditions préalables à l’étape 3 auxquelles vous pouvez accéder en cliquant sur la liste déroulante sous le titre étape 3.
    
    b. Cliquez sur **exécuter** à l’étape 3 pour lancer l’Assistant Préparation de la forêt actuelle.
    
    c. Notez que la procédure ne doit être exécutée qu’une seule fois par déploiement, puis cliquez sur **suivant**.
    
    d. Spécifiez le domaine dans lequel les groupes universels seront créés. Si le serveur fait partie du domaine, vous pouvez choisir **domaine local**, puis cliquez sur **suivant**.
    
    e. Une fois que la forêt a été préparée, vous pouvez afficher le journal en cliquant sur **afficher le journal**. 
    
    f. Cliquez sur **Terminer** pour fermer l’Assistant préparer la forêt actuelle et revenir aux étapes préparer Active Directory.
    
    g. Cliquez sur **Skype entreprise Server Management Shell** à partir de la page **apps** pour lancer PowerShell.
    
    h. Tapez la commande Get-CsAdForest, puis appuyez sur **entrée**.
    
    Je. Si le résultat est **LC_FORESTSETTINGS_STATE_READY**, la forêt a été préparée correctement, comme illustré dans la figure.
    
     ![Vérifier la réplication de la forêt.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Étape 4 : vérifier la réplication du catalogue global**
    
    a. Sur un contrôleur de domaine (de préférence sur un site distant par rapport aux autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été exécutée, ouvrez **utilisateurs et ordinateurs Active Directory**.
    
    b. Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.
    
    c. Cliquez sur le conteneur **utilisateurs** dans le volet gauche, puis recherchez le groupe universel **CsAdministrator** dans le volet droit. Si CsAdministrator (parmi les autres nouveaux groupes universels qui commencent par le protocole CS) est présent, la réplication Active Directory a réussi.
    
    d. Si les groupes ne sont pas encore présents, vous pouvez forcer la réplication ou patienter 15 minutes et actualiser le volet droit. Lorsque les groupes apparaissent, la réplication est terminée.
    
8. **Étape 5 : préparer le domaine actuel**
    
    a. Passez en revue les informations requises pour l’étape 5.
    
    b. Cliquez sur **exécuter** à l’étape 5 pour lancer l’Assistant préparer le domaine actuel.
    
    c. Notez que la procédure ne doit être exécutée qu’une seule fois pour chaque domaine dans le déploiement, puis cliquez sur **suivant**.
    
    d. Une fois que le domaine a été préparé, vous pouvez afficher le journal en cliquant sur **afficher le journal**. 
    
    e. Cliquez sur **Terminer** pour fermer l’Assistant préparer le domaine actuel et revenir aux étapes préparer Active Directory.
    
    Ces étapes doivent être effectuées dans chaque domaine où les objets Skype entreprise Server sont trouvés, sinon les services peuvent ne pas démarrer. Cela inclut tous les types d’objets Active Directory, tels que les utilisateurs, les objets contact, les groupes d’administration ou tout autre type d’objet. Vous pouvez utiliser SET-CsUserReplicatorConfiguration-ADDomainNamingContextList pour ajouter uniquement les domaines avec des objets Skype entreprise Server, si nécessaire.
    
9. **Étape 6 : vérifier la réplication dans le domaine**
    
    a. Cliquez sur **Skype entreprise Server Management Shell** à partir de la page **apps** pour lancer PowerShell.
    
    b. Utilisez la commande Get-CsAdDomain pour vérifier la réplication dans le domaine.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Si vous omettez le paramètre Domain, le domaine local est utilisé. 
  
    Exemple d’exécution de la commande pour le domaine contoso. local :
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > À l’aide du paramètre GlobalSettingsDomainController, vous pouvez indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (ce qui est normal dans les déploiements de mise à niveau dont le paramètre global n’a pas été migré vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt AD DS. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous définissez tout contrôleur de domaine de la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande part du principe que les paramètres sont stockés dans le conteneur de configuration et font référence à n’importe quel contrôleur de domaine dans Active Directory. 
  
    c. Si le résultat est **LC_DOMAINSETTINGS_STATE_READY**, le domaine a été répliqué avec succès.
    
10. **Étape 7 : ajouter des utilisateurs pour fournir un accès administratif au panneau de configuration de Skype entreprise Server**
    
    a. Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.
    
    b. Ouvrez **utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez sur le conteneur **utilisateurs** , cliquez avec le bouton droit sur CSAdministrator, puis choisissez **Propriétés**.
    
    c. Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.
    
    d. Sous l'onglet **Membres**, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.
    
    e. Dans l’onglet **membres** , confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.
    
    > [!CAUTION]
    > Le panneau de configuration de Skype entreprise Server est un outil de contrôle d’accès basé sur un rôle. L’appartenance au groupe CsAdministrator permet à un utilisateur qui utilise le panneau de configuration de Skype entreprise Server d’utiliser le contrôle total pour toutes les fonctions de configuration disponibles. D’autres rôles conçus pour des fonctions spécifiques sont disponibles. Pour plus d’informations sur les rôles disponibles, reportez-vous à [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Notez que les utilisateurs n’ont pas besoin d’être activés pour Skype entreprise Server afin d’être membres des groupes de gestion. 
  
    > [!CAUTION]
    > Pour préserver la sécurité et l’intégrité du contrôle d’accès basé sur un rôle, ajoutez des utilisateurs aux groupes qui définissent le rôle que l’utilisateur effectue dans la gestion du déploiement de Skype entreprise Server. 
  
11. Déconnectez-vous, puis reconnectez-vous à Windows afin que votre jeton de sécurité soit mis à jour avec le nouveau groupe de sécurité de Skype entreprise Server, puis rouvrez l’Assistant déploiement.
    
12. Vérifiez que vous voyez une coche verte en regard de **Préparer Active Directory** pour confirmer la réussite, comme illustré dans la figure.
    
     ![Préparation d’Active Directory terminée.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Voir aussi
 
[Services de domaine Active Directory pour Skype entreprise Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
