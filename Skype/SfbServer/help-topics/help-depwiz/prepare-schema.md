---
titre : « Préparer le schéma » ms.author : jambirk auteur : Gestionnaire de jambirk : serdars ms.date : ms.audience de 2/8/2018 : ITPro ms.topic : article de f1_keywords :
- ms.lync.dep.DeployMainSchemaPrep ms.prod : localization_priority de Skype pour entreprise itpro : ms.assetid Normal : 337aa234-c5f3-4468-a047-2023848e942c description : « pour préparer le schéma des Services de domaine Active Directory, vous exécutez le schéma de la préparation étape le Skype pour l’Assistant de déploiement de Business Server. Cliquez sur Exécuter pour commencer la préparation du schéma. L’étape Préparer un schéma lit les fichiers de définition de schéma fournis dans le répertoire \Program Files\Microsoft Lync Server 2013\Deployment\Setup sur le système sur lequel l’Assistant Déploiement s’exécute. Ces fichiers sont également disponibles sur le support d’installation, dans le répertoire \Support\Schema. L’étape Préparer un schéma développera le schéma et rapportera le statut du processus. Elle vous notifiera également l’achèvement du processus. L’écran de résumé vous permettra d’afficher les journaux du processus. Passez en revue les journaux pour vous assurer que la préparation a été terminée et réussie. »
---

# <a name="prepare-schema"></a>Préparer un schéma
 
Pour préparer le schéma Active Directory Domain Services, pour exécuter l’étape de préparation de schéma dans le Skype pour l’Assistant de déploiement de Business Server. Cliquez sur **Exécuter** pour commencer la préparation du schéma. L’étape Préparer un schéma lit les fichiers de définition de schéma fournis dans le répertoire \Program Files\Microsoft Lync Server 2013\Deployment\Setup sur le système sur lequel l’Assistant Déploiement s’exécute. Ces fichiers sont également disponibles sur le support d’installation, dans le répertoire \Support\Schema. L’étape Préparer un schéma développera le schéma et rapportera le statut du processus. Elle vous notifiera également l’achèvement du processus. L’écran de résumé vous permettra d’afficher les journaux du processus. Passez en revue les journaux pour vous assurer que la préparation est terminée et qu’elle a abouti.
  
> [!IMPORTANT]
> Pour étendre le schéma, vous devez être connecté au domaine en tant que membre du groupe Administrateurs du schéma et du groupe Administrateurs d’entreprise. 
  
Classes et attributs sont ajoutés pour étendre le schéma Active Directory Domain Services pour prendre en charge Skype pour serveur Business Server 2015, de service et les objets utilisateur. Avant d’étendre le schéma, effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le rôle de contrôleur de schéma. Pour plus d’informations sur le processus de sauvegarde de Windows Server 2008 R2 avec SP1, consultez [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198). Pour Windows Server 2003 et Windows Server 2003 R2, consultez [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).
  
> [!CAUTION]
> Cette opération est irréversible. Vous devez faire tout votre possible pour limiter l’impact potentiel d’un échec de l’extension du schéma et pour garantir la réussite de l’extension du schéma. Ceci est particulièrement important en cas de perte de communication ou de toute autre défaillance côté serveur. Vous devez effectuer une sauvegarde du contrôleur de domaine maître du schéma et une sauvegarde complète d’Active Directory. 
  
Pour effectuer une sauvegarde du contrôleur de domaine maître du schéma et une sauvegarde complète d’Active Directory :
  
1. Déconnectez du réseau le contrôleur de domaine qui contient le rôle de contrôleur de schéma.
    
2. Effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le contrôleur de schéma.
    
3. Étendez le schéma.
    
4. Lorsque l’extension aboutit, reconnectez le contrôleur de domaine au réseau et assurez-vous que la réplication est active et qu’elle fonctionne.
    
5. Dans l’éventualité d’une défaillance d’extension de schéma, restaurez l’état système du contrôleur de domaine et Active Directory à l’aide de la sauvegarde d’état du système que vous avez prises plus haut.
    
> [!NOTE]
> Si vous devez passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement de Business Server, vous pouvez trouver les fichiers sur l’ordinateur où l’Assistant de déploiement a été exécuté, dans le répertoire des utilisateurs de l’utilisateur Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

