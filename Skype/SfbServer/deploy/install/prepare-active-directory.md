---
title: Préparation d’Active Directory pour Skype Entreprise Server 2015
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
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Résumé : Découvrez comment préparer votre domaine Active Directory pour une installation de Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour Business Server 2015 depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6dfd6452e2ff0296fdeb90bd4f81296efac2be62
ms.sourcegitcommit: 4eae947e339e728e5e1f338677860b910aafc029
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Préparation d’Active Directory pour Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment préparer votre domaine Active Directory pour une installation de Skype Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour Business Server 2015 à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype pour Business Server travaille en étroite collaboration avec Active Directory. Vous devez préparer le domaine Active Directory pour fonctionner avec Skype pour Business Server. Ce processus est effectué dans l’Assistant Déploiement et s’effectue uniquement une seule fois pour le domaine. Ceci est dû au fait que le processus crée des groupes et modifie le domaine et vous n’avez besoin d’effectuer cette opération qu’une seule fois. Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5 comme indiqué dans le diagramme. Préparation d’Active Directory est l’étape 4 de 8. Pour plus d’informations sur la planification d’Active Directory, consultez [exigences pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![schéma de vue d’ensemble](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Préparer Active Directory

Skype pour Business Server 2015 est étroitement intégré aux Services de domaine Active Directory (AD DS). Avant d’installer Skype pour Business Server 2015 pour la première fois, Active Directory doivent être préparé. La section de l’Assistant Déploiement intitulée **Préparer Active Directory** prépare l’environnement Active Directory pour une utilisation avec Skype pour Business Server.
  
> [!NOTE]
> Skype pour Business Server 2015 utilise (AD DS) pour effectuer le suivi et de communiquer avec tous les serveurs dans une topologie. Chaque serveur doit être joint au domaine afin que Skype pour Business Server fonctionne correctement. 
  
> [!IMPORTANT]
> La procédure Préparer Active Directory ne doit être effectuée qu’une seule fois pour chaque domaine du déploiement. 
  
Regardez en vidéo les étapes pour **préparer Active Directory** :
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Préparation d’Active Directory à partir de l’Assistant déploiement

1. Connectez-vous comme utilisateur avec des données d’identification d’administrateur de schéma pour le domaine Active Directory.
    
2. Ouvrez Skype pour l’Assistant de déploiement Business Server.
    
    > [!TIP]
    > Si vous souhaitez consulter les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement Business Server, vous pouvez trouver les sur l’ordinateur où a été exécuté l’Assistant déploiement, dans le répertoire des utilisateurs de l’utilisateur de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur est connecté en tant qu’administrateur de domaine dans le domaine, contoso.local, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Cliquez sur le lien **Préparer Active Directory**.
    
4. **Étape 1 : Préparer un schéma**
    
    a. Passez en revue les informations requises pour l’étape 1, qui sont accessibles par un clic sur la liste déroulante sous le titre de l’étape 1.
    
    b. Cliquez sur **Exécuter** dans l’étape 1 pour lancer l’assistant Préparer le schéma.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque déploiement. Cliquez alors sur **Suivant**.
    
    d. Une fois que le schéma a été préparé, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    e. Cliquez sur **Terminer** pour fermer l’assistant Préparer le schéma et revenez aux étapes de préparation d’Active Directory.
    
5. **Étape 2 : Vérifier la réplication de la partition du schéma**
    
    a. Connectez-vous au contrôleur de domaine pour le domaine en question.
    
    b. Ouvrez **Modification ADSI** à partir du menu déroulant **Outils** dans **Gestionnaire de serveur**.
    
    c. Dans le menu **Action**, cliquez sur **Connexion**.
    
    d. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
    e. Sous le conteneur de schéma, recherchez **CN=ms-RTC-SIP-SchemaVersion**. Si cet objet existe et si la valeur de l’attribut **rangeUpper** est 1150 et si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès. Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.
    
6. **Étape 3 : Préparer la forêt actuelle**
    
    a. Passez en revue les informations requises pour l’étape 3, qui sont accessibles par un clic sur la liste déroulante sous le titre de l’étape 3.
    
    b. Cliquez sur **Exécuter** dans l’étape 3 pour lancer l’assistant Préparer la forêt actuelle.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque déploiement. Cliquez alors sur **Suivant**.
    
    d. Précisez le domaine dans lequel les groupes universels seront créés. Si le serveur fait partie du domaine, vous pouvez choisir **Domaine local** et cliquer sur **Suivant**.
    
    e. Une fois que la forêt a été préparée, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    f. Cliquez sur **Terminer** pour fermer l’assistant Préparer la forêt actuelle et revenez aux étapes de préparation d’Active Directory.
    
    g. Cliquez sur **Skype pour Business Server Management Shell** dans la page **applications** pour lancer PowerShell.
    
    h. Tapez la commande Get-CsAdForest, puis appuyez sur **entrée**.
    
    i. Si le résultat est **LC_FORESTSETTINGS_STATE_READY**, la forêt a correctement été préparée, comme illustré dans la figure.
    
     ![Vérification de la réplication de forêt.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Étape 4 : Vérifier la réplication du catalogue global**
    
    a. Sur un contrôleur de domaine (de préférence sur un site distant par rapport aux autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été effectuée, ouvrez **Utilisateurs et ordinateurs Active Directory**.
    
    b. Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.
    
    c. Cliquez sur le conteneur **Utilisateurs** dans le volet de gauche et recherchez le groupe universel **CsAdministrator** dans le volet de droite. Si CsAdministrator (parmi huit autres nouveaux groupes universels commençant par Cs) est présent, la réplication d’Active Directory a réussi.
    
    d. Si les groupes ne sont pas encore présents, vous pouvez forcer la réplication ou attendre 15 minutes, puis actualiser le volet de droite. Lorsque les groupes apparaissent, la réplication est terminée.
    
8. **Étape 5 : Préparer le domaine actuel**
    
    a. Passez en revue les informations requises pour l’étape 5.
    
    b. Cliquez sur **Exécuter** dans l’étape 5 pour lancer l’assistant Préparer le domaine actuel.
    
    c. Veuillez remarquer qu’il suffit de suivre la procédure une seule fois pour chaque domaine du déploiement. Cliquez alors sur **Suivant**.
    
    d. Une fois que le domaine a été préparé, vous pouvez voir le journal en cliquant sur **Afficher le journal**. 
    
    e. Cliquez sur **Terminer** pour fermer l’assistant Préparer le domaine actuel et revenez aux étapes de préparation d’Active Directory.
    
    Ces étapes doivent être effectuées dans chaque domaine où Skype pour les objets Business Server sont détectés, sinon services peut pas démarrer. Il peut notamment s’agir de n’importe quel objet Active Directory, tel qu’utilisateurs, objets de contact, groupes administratifs, ou tout autre objet. Vous pouvez utiliser Set-CsUserReplicatorConfiguration - ADDomainNamingContextList pour ajouter uniquement les domaines avec Skype pour les objets Business Server, le cas échéant.
    
9. **Étape 6 : Vérifier la réplication dans le domaine**
    
    a. Cliquez sur **Skype pour Business Server Management Shell** dans la page **applications** pour lancer PowerShell.
    
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
  
    c. Si le résultat est **lc_domain_settings_state_ready**, le domaine a été répliqué avec succès.
    
10. **Étape 7 : Ajouter des utilisateurs pour fournir un accès administratif à la Skype pour Business Server Control Panel**
    
    a. Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.
    
    b. Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez sur le conteneur **Utilisateurs**, cliquez avec le bouton droit sur CSAdministrator, puis choisissez **Propriétés**.
    
    c. Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.
    
    d. Sous l’onglet **Membres**, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.
    
    e. Sous l’onglet **Membres**, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.
    
    > [!CAUTION]
    > Le Skype pour Business Server Control Panel est un outil de contrôle d’accès basé sur un rôle. L’appartenance au groupe CsAdministrator donne à un utilisateur qui utilise le Skype pour le panneau de configuration serveur Business un contrôle total sur toutes les fonctions de configuration disponibles. Il existe d’autres rôles disponibles conçus pour des fonctions spécifiques. Pour plus d’informations sur les rôles disponibles, consultez [exigences pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Notez que les utilisateurs ne doivent pas être activé pour Skype pour Business Server afin de devenir membres des groupes d’administration. 
  
    > [!CAUTION]
    > Pour préserver la sécurité et l’intégrité de contrôle d’accès basé sur un rôle, ajouter des utilisateurs aux groupes qui définissent le rôle tenu par l’utilisateur dans la gestion de la Skype pour le déploiement de serveur d’entreprise. 
  
11. Déconnectez-vous, puis reconnectez-vous à Windows afin que votre jeton de sécurité est mis à jour avec la nouvelle Skype pour le groupe de sécurité Business Server et puis rouvrez l’Assistant déploiement.
    
12. Vérifiez la présence d’une coche verte à côté de **Préparer Active Directory** pour confirmer que vous avez réussi, comme indiqué dans la figure.
    
     ![Préparation d’Active Directory terminée.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Voir aussi

#### 
[Services de domaine Active Directory pour Skype pour Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)