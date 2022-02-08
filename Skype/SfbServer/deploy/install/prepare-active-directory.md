---
title: 'Skype Entreprise Server : préparer Active Directory'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: "Résumé : Découvrez comment préparer votre domaine Active Directory pour une installation de Skype Entreprise Server. Téléchargez une version d’évaluation Skype Entreprise Server gratuite à partir du Centre d’évaluation Microsoft à l':. https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server"
ms.openlocfilehash: 9f9ea53c95e2db94d8e47da7deca285f4bb148cf
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392226"
---
# <a name="skype-for-business-server-prepare-active-directory"></a>Skype Entreprise Server : préparer Active Directory
 
**Résumé :** Découvrez comment préparer votre domaine Active Directory pour une installation de Skype Entreprise Server. Téléchargez une version d’évaluation Skype Entreprise Server gratuite à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype Entreprise Server fonctionne en étroite collaboration avec Active Directory. Vous devez préparer le domaine Active Directory à l’Skype Entreprise Server. Ce processus est réalisé dans l’Assistant Déploiement et n’est effectué qu’une seule fois pour le domaine. En effet, le processus crée des groupes et modifie le domaine, et vous ne devez le faire qu’une seule fois. Vous pouvez suivre les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez suivre les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. La préparation d’Active Directory est l’étape 4 sur 8. Pour plus d’informations sur la planification d’Active Directory, voir [Environmental requirements for Skype Entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype Entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagramme de vue d’ensemble.](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Préparer Active Directory

Skype Entreprise Server est étroitement intégré aux services de domaine Active Directory (AD DS). Avant Skype Entreprise Server être installé pour la première fois, Active Directory doit être préparé. La section de l’Assistant Déploiement intitulée **Préparer Active Directory** prépare l’environnement Active Directory à utiliser avec Skype Entreprise Server.
  
> [!NOTE]
> Skype Entreprise Server utilise (AD DS) pour suivre et communiquer avec tous les serveurs d’une topologie. La plupart de ces serveurs doivent être joints au domaine pour que Skype Entreprise Server fonctionne correctement. N’oubliez pas que les serveurs tels que edge et proxy inverse ne doivent pas être joints au domaine.
  
> [!IMPORTANT]
> La procédure Préparer Active Directory ne doit être exécuté qu’une seule fois pour chaque domaine du déploiement. 
  
Regardez les étapes de la vidéo **pour préparer Active Directory** :
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Préparer Active Directory à partir de l’Assistant Déploiement

1. Connectez-vous en tant qu’utilisateur avec les informations d’identification Administrateurs du schéma pour le domaine Active Directory.
    
2. Ouvrez Skype Entreprise Server’Assistant Déploiement.
    
    > [!TIP]
    > Si vous souhaitez passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté, dans le répertoire Utilisateurs de l’utilisateur AD DS qui a exécuté l’étape. Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le domaine, contoso.local, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Cliquez sur **le lien Préparer Active Directory** .
    
4. **Étape 1 : Préparer le schéma**
    
    a. Consultez les informations des conditions préalables pour l’étape 1 qui sont accessibles en cliquant sur la drop-down sous le titre de l’étape 1.
    
    b. Cliquez **sur Exécuter** à l’étape 1 pour lancer l’Assistant Préparer le schéma.
    
    c. Notez que la procédure ne doit être exécuté qu’une seule fois pour chaque déploiement, puis cliquez sur **Suivant**.
    
    d. Une fois le schéma préparé, vous pouvez afficher le journal en cliquant sur **Afficher le journal**. 
    
    e. Cliquez **sur Terminer** pour fermer l’Assistant Préparer le schéma et revenir aux étapes Préparer Active Directory.
    
5. **Étape 2 : Vérifier la réplication de la partition de schéma**
    
    a. Connectez-vous au contrôleur de domaine pour le domaine.
    
    b. **Ouvrez ADSI Edit à** partir du menu déroulant **Outils** dans **le Gestionnaire de serveur**.
    
    c. Dans le menu **Action**, cliquez sur **Connexion à**.
    
    d. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
    e. Sous le conteneur de schéma, recherchez **CN=ms-RTC-SIP-SchemaVersion**. Si cet objet existe et que la valeur de l’attribut **rangeUpper** est 1150 et que la valeur de l’attribut **rangeLower** est 3, le schéma a été correctement mis à jour et répliqué. Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas telles que spécifiées, le schéma n’a pas été modifié ou n’a pas été répliqué.
    
6. **Étape 3 : Préparer la forêt actuelle**
    
    a. Consultez les informations des conditions préalables pour l’étape 3 qui sont accessibles en cliquant sur la drop-down sous le titre de l’étape 3.
    
    b. Cliquez **sur Exécuter** à l’étape 3 pour lancer l’Assistant Préparer la forêt actuelle.
    
    c. Notez que la procédure ne doit être exécuté qu’une seule fois par déploiement, puis cliquez sur **Suivant**.
    
    d. Spécifiez le domaine dans lequel les groupes universels seront créés. Si le serveur fait partie du domaine, vous pouvez choisir domaine **local**, puis cliquer sur **Suivant**.
    
    e. Une fois la forêt préparée, vous pouvez afficher le journal en cliquant sur **Afficher le journal**. 
    
    f. Cliquez **sur Terminer** pour fermer l’Assistant Préparer la forêt actuelle et revenir aux étapes Préparer Active Directory.
    
    g. Cliquez **Skype Entreprise Server Management Shell à** partir de la page **Applications** pour lancer PowerShell.
    
    h. Tapez la commande Get-CsAdForest, puis appuyez sur **Entrée**.
    
    i. Si le résultat est **LC_FORESTSETTINGS_STATE_READY**, la forêt a été préparée avec succès, comme illustré dans la figure.
    
     ![Vérifiez la réplication de la forêt.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Étape 4 : Vérifier la réplication du catalogue global**
    
    a. Sur un contrôleur de domaine (de préférence dans un site distant à partir des autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été exécuté, ouvrez Utilisateurs et ordinateurs **Active Directory**.
    
    b. Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.
    
    c. Cliquez sur **le conteneur Utilisateurs** dans le volet gauche, puis recherchez le groupe universel **CsAdministrator** dans le volet de droite. Si CsAdministrator (parmi les nouveaux groupes universels qui commencent par Cs) est présent, la réplication Active Directory a réussi.
    
    d. Si les groupes ne sont pas encore présents, vous pouvez forcer la réplication, ou attendre 15 minutes et actualiser le volet de droite. Lorsque les groupes apparaissent, la réplication est terminée.
    
8. **Étape 5 : Préparer le domaine actuel**
    
    a. Examinez les informations des conditions préalables pour l’étape 5.
    
    b. Cliquez **sur Exécuter** à l’étape 5 pour lancer l’Assistant Préparer le domaine actuel.
    
    c. Notez que la procédure ne doit être exécuté qu’une seule fois pour chaque domaine du déploiement, puis cliquez sur **Suivant**.
    
    d. Une fois que le domaine a été préparé, vous pouvez afficher le journal en cliquant **sur Afficher le journal**. 
    
    e. Cliquez **sur Terminer** pour fermer l’Assistant Préparer le domaine actuel et revenir aux étapes Préparer Active Directory.
    
    Ces étapes doivent être effectuées dans chaque domaine où des objets Skype Entreprise Server sont trouvés, sinon les services peuvent ne pas démarrer. Cela inclut tout type d’objet Active Directory, tel que les utilisateurs, les objets contact, les groupes d’administration ou tout autre type d’objet. Vous pouvez utiliser Set-CsUserReplicatorConfiguration -ADDomainNamingContextList pour ajouter uniquement les domaines avec Skype Entreprise Server objets, si nécessaire.
    
9. **Étape 6 : Vérifier la réplication dans le domaine**
    
    a. Cliquez sur le **Skype Entreprise Server Management Shell à** partir de la page **Applications** pour lancer PowerShell.
    
    b. Utilisez la commande Get-CsAdDomain vérifier la réplication dans le domaine.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Si vous omettez le paramètre Domain, le domaine local est utilisé. 
  
    Exemple d’exécution de la commande pour le domaine contoso.local :
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > En utilisant le paramètre GlobalSettingsDomainController, vous pouvez indiquer où les paramètres globaux sont stockés. Si vos paramètres sont stockés dans le conteneur système (ce qui est typique des déploiements de mise à niveau pour lesquels le paramètre global n’a pas été migré vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt AD DS. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous définissez tout contrôleur de domaine de la forêt. Si vous ne spécifiez pas ce paramètre, la cmdlet suppose que les paramètres sont stockés dans le conteneur de configuration et fait référence à n’importe quel contrôleur de domaine dans Active Directory. 
  
    c. Si le résultat est **LC_DOMAINSETTINGS_STATE_READY**, le domaine a été répliqué avec succès.
    
10. **Étape 7 : Ajouter des utilisateurs pour fournir un accès administratif au Panneau de Skype Entreprise Server de gestion**
    
    a. Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.
    
    b. **Ouvrez Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez sur le conteneur Utilisateurs, cliquez avec le bouton droit sur CSAdministrator et choisissez **Propriétés**.
    
    c. Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.
    
    d. Sous l'onglet **Membres**, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.
    
    e. Sous **l’onglet** Membres, confirmez que les utilisateurs ou groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.
    
    > [!CAUTION]
    > Le Skype Entreprise Server de contrôle d’accès est un outil de contrôle d’accès basé sur un rôle. L’appartenance au groupe CsAdministrator donne à un utilisateur qui utilise le Panneau de configuration Skype Entreprise Server un contrôle total pour toutes les fonctions de configuration disponibles. D’autres rôles conçus pour des fonctions spécifiques sont disponibles. Pour plus d’informations sur les rôles disponibles, voir [Environmental requirements for Skype Entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype Entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md). Notez que les utilisateurs n’ont pas besoin d’être activés pour Skype Entreprise Server pour être membres des groupes de gestion. 
  
    > [!CAUTION]
    > Pour vous aider à conserver la sécurité et l’intégrité du contrôle d’accès basé sur les rôles, ajoutez des utilisateurs aux groupes qui définissent le rôle que l’utilisateur joue dans la gestion du Skype Entreprise Server déploiement. 
  
11. Déconnectez-vous, puis rouvrez une session sur Windows afin que votre jeton de sécurité soit mis à jour avec le nouveau groupe de sécurité Skype Entreprise Server, puis rouvrez l’Assistant Déploiement.
    
12. Vérifiez que vous voyez une coche verte en regard de **Préparer Active Directory** pour confirmer la réussite, comme illustré dans la figure.
    
     ![Préparer Active Directory terminé.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Voir aussi
 
[Services de domaine Active Directory pour Skype Entreprise Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
