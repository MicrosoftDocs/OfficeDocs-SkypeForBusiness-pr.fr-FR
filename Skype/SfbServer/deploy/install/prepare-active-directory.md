---
title: Préparer Active Directory pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Résumé: Découvrez comment préparer votre domaine Active Directory pour l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: e15431cf08925920f4f7ec223d9983d3dc3e35c7
ms.sourcegitcommit: 46fb558814cb6bd7d70729eac590afd51fc6606e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2019
ms.locfileid: "35002844"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Préparer Active Directory pour Skype entreprise Server
 
**Résumé:** Découvrez comment préparer votre domaine Active Directory pour l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype entreprise Server fonctionne étroitement avec Active Directory. Vous devez préparer le domaine Active Directory pour qu’il fonctionne avec Skype entreprise Server. Ce processus est réalisé dans l’Assistant Déploiement et n’est effectué qu’une seule fois pour le domaine. Ceci est dû au fait que le processus crée des groupes et modifie le domaine et vous n’avez besoin d’effectuer cette opération qu’une seule fois. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez suivre les étapes 6,7 et 8 dans l’ordre et après avoir effectué les étapes 1 à 5, comme expliqué dans le diagramme. La préparation d’Active Directory est étape 4 sur 8. Pour plus d’informations sur la planification d’Active Directory, reportez-vous à la section [configuration environnementale requise pour Skype entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [serveur requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![schéma de vue d’ensemble](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Préparer Active Directory

Skype entreprise Server est étroitement intégré avec les services de domaine Active Directory (AD DS). Pour que Skype entreprise Server puisse être installé pour la première fois, Active Directory doit être préparé. Section de l’Assistant Déploiement intitulée **Préparer Active Directory** prépare l’environnement Active Directory pour une utilisation avec Skype entreprise Server.
  
> [!NOTE]
> Skype entreprise Server utilise (AD DS) pour suivre et communiquer avec tous les serveurs d’une topologie. Chaque serveur doit être joint au domaine de sorte que Skype entreprise Server puisse fonctionner correctement. 
  
> [!IMPORTANT]
> La procédure Préparer Active Directory ne doit être effectuée qu’une seule fois pour chaque domaine du déploiement. 
  
Regardez en vidéo les étapes pour **préparer Active Directory** :
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Préparation d’Active Directory à partir de l’Assistant déploiement

1. Connectez-vous comme utilisateur avec des données d’identification d’administrateur de schéma pour le domaine Active Directory.
    
2. Ouvrez l’Assistant Déploiement de Skype entreprise Server.
    
    > [!TIP]
    > Si vous souhaitez consulter les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise, vous pouvez les retrouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté, dans l’annuaire utilisateurs de l’utilisateur AD DS qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans Domain, contoso. local, les fichiers journaux se trouvent dans: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Cliquez sur le lien **Préparer Active Directory**.
    
4. **Étape 1 : Préparer le schéma**
    
    a. Passez en revue les informations requises pour l’étape 1, qui sont accessibles par un clic sur la liste déroulante sous le titre de l’étape 1.
    
    b. Cliquez sur **Exécuter** dans l’étape 1 pour lancer l’assistant Préparer le schéma.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque déploiement. Cliquez alors sur **Suivant**.
    
    d. Une fois que le schéma a été préparé, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    e. Cliquez sur **Terminer** pour fermer l’assistant Préparer le schéma et revenez aux étapes de préparation d’Active Directory.
    
5. **Étape 2 : Vérifier la réplication de la partition du schéma**
    
    a. Connectez-vous au contrôleur de domaine pour le domaine en question.
    
    b. Ouvrez **Modification ADSI** à partir du menu déroulant **Outils** dans **Gestionnaire de serveur**.
    
    c. Dans le menu **Action**, cliquez sur **Connexion**.
    
    d. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
    e. Sous le conteneur de schéma, recherchez **CN=ms-RTC-SIP-SchemaVersion**. Si cet objet existe et si la valeur de l’attribut **rangeUpper** est 1150 et si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès. Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.
    
6. **Étape 3 : Préparer la forêt actuelle**
    
    a. Passez en revue les informations requises pour l’étape 3, qui sont accessibles par un clic sur la liste déroulante sous le titre de l’étape 3.
    
    b. Cliquez sur **Exécuter** dans l’étape 3 pour lancer l’assistant Préparer la forêt actuelle.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque déploiement. Cliquez alors sur **Suivant**.
    
    d. Précisez le domaine dans lequel les groupes universels seront créés. Si le serveur fait partie du domaine, vous pouvez choisir **Domaine local** et cliquer sur **Suivant**.
    
    e. Une fois que la forêt a été préparée, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    touche. Cliquez sur **Terminer** pour fermer l’assistant Préparer la forêt actuelle et revenez aux étapes de préparation d’Active Directory.
    
    grand. Cliquez sur **Skype entreprise Server Management Shell** à partir de la page **applications** pour lancer PowerShell.
    
    h. Tapez la commande Get-CsAdForest, puis appuyez sur **entrée**.
    
    ma. S’il s’agit de **LC_FORESTSETTINGS_STATE_READY**, la forêt a bien été préparée, comme indiqué dans l’illustration.
    
     ![Vérification de la réplication de forêt.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Étape 4 : Vérifier la réplication du catalogue global**
    
    a. Sur un contrôleur de domaine (de préférence sur un site distant par rapport aux autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été effectuée, ouvrez **Utilisateurs et ordinateurs Active Directory**.
    
    b. Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.
    
    c. Cliquez sur le conteneur **Utilisateurs** dans le volet de gauche et recherchez le groupe universel **CsAdministrator** dans le volet de droite. Si CsAdministrator (parmi huit autres nouveaux groupes universels commençant par Cs) est présent, la réplication d’Active Directory a réussi.
    
    d. Si les groupes ne sont pas encore présents, vous pouvez forcer la réplication ou attendre 15 minutes, puis actualiser le volet de droite. Lorsque les groupes apparaissent, la réplication est terminée.
    
8. **Étape 5 : Préparer le domaine actuel**
    
    a. Passez en revue les informations requises pour l’étape 5.
    
    b. Cliquez sur **Exécuter** dans l’étape 5 pour lancer l’assistant Préparer le domaine actuel.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque domaine du déploiement. Cliquez alors sur **Suivant**.
    
    d. Une fois que le domaine a été préparé, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    e. Cliquez sur **Terminer** pour fermer l’assistant Préparer le domaine actuel et revenez aux étapes de préparation d’Active Directory.
    
    Ces étapes doivent être achevées dans tous les domaines dans lesquels les objets Skype entreprise Server sont trouvés, sinon les services risquent de ne pas démarrer. Il peut notamment s’agir de n’importe quel objet Active Directory, tel qu’utilisateurs, objets de contact, groupes administratifs, ou tout autre objet. Le cas échéant, vous pouvez utiliser SET-CsUserReplicatorConfiguration-ADDomainNamingContextList pour ajouter uniquement les domaines contenant des objets Skype entreprise Server.
    
9. **Étape 6 : Vérifier la réplication dans le domaine**
    
    a. Dans la page **applications** , cliquez sur **Skype entreprise Server Management Shell** pour lancer PowerShell.
    
    b. Utilisez la commande Get-CsAdDomain pour vérifier la réplication au sein du domaine.
    
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
  
    c. Si le résultat est **LC_DOMAINSETTINGS_STATE_READY**, le domaine a été correctement répliqué.
    
10. **Étape 7 : Ajouter des utilisateurs pour fournir l’accès administratif au Panneau de configuration de Skype Entreprise Server**
    
    a. Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.
    
    b. Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez sur le conteneur **Utilisateurs**, cliquez avec le bouton droit sur CSAdministrator, puis choisissez **Propriétés**.
    
    c. Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.
    
    d. Sous l’onglet **Membres**, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.
    
    e. Sous l’onglet **Membres**, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.
    
    > [!CAUTION]
    > Le panneau de configuration Skype entreprise Server est un outil de contrôle d’accès basé sur un rôle. L’appartenance au groupe CsAdministrator donne à un utilisateur qui utilise le panneau de configuration Skype entreprise Server un contrôle total pour toutes les fonctions de configuration disponibles. D’autres rôles conçus pour des fonctions spécifiques sont disponibles. Pour plus d’informations sur les rôles disponibles, voir [Configuration requise pour Skype entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [serveur requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md). Notez que les utilisateurs n’ont pas besoin d’être activés pour Skype entreprise Server afin de pouvoir être ajoutés aux groupes de gestion. 
  
    > [!CAUTION]
    > Pour garantir la sécurité et l’intégrité des contrôles d’accès basée sur les rôles, ajoutez des utilisateurs aux groupes qui déterminent le rôle que l’utilisateur effectue dans la gestion du déploiement de Skype entreprise Server. 
  
11. Déconnectez-vous, puis reconnectez-vous à Windows afin de mettre à jour votre jeton de sécurité avec le nouveau groupe de sécurité Skype entreprise Server, puis rouvrez l’Assistant déploiement.
    
12. Vérifiez qu’une coche verte s’affiche en regard de **Préparer Active Directory** pour confirmer la réussite, comme illustré dans la figure.
    
     ![Préparation d’Active Directory terminée.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Voir aussi
 
[Active Directory Domain Services for Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
