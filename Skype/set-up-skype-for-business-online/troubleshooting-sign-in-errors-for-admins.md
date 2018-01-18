---
title: "Résolution des problèmes de Skype pour les erreurs de connexion en ligne Business pour les administrateurs"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Découvrez les causes courantes de Skype pour Business Online-erreurs de connexion et de travail grâce à la résolution de ces problèmes. "
ms.openlocfilehash: 55ef2775ecc2f04fe9ce89dc8691c9186512a0e0
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Résolution des problèmes de Skype pour les erreurs de connexion en ligne Business pour les administrateurs

Pour résoudre les problèmes de Skype pour les erreurs de connexion en ligne Business, démarrez en éliminant les causes les plus courantes de difficultés de connexion. Si nécessaire, vous pouvez alors suivre les étapes en fonction du type d’erreur de résolution spécifique. Si l’utilisateur ne peut pas toujours signer, collecter des informations supplémentaires et ensuite pour obtenir une assistance supplémentaire. 
  
## <a name="what-do-you-want-to-do"></a>Que voulez-vous faire ?
<a name="top"> </a>

> [Rechercher les causes courantes de Skype pour les erreurs de connexion Business en ligne](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
    
> [Suivez les étapes de résolution d’une erreur spécifique (Enterprise seulement)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
    
> [Ajouter une entrée de pare-feu pour msoidsvc.exe à votre serveur proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
    
> [Mettre à jour les paramètres DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
    
> [Installer un certificat SSL de tiers sur votre serveur ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
    
> [Mettre à jour les informations d’identification de sécurité](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
    
> [Modifier des clés de Registre TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
    
> [Mettre à jour les paramètres de l’utilisateur dans Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
    
> [Utiliser le guide de dépannage de Support de Microsoft](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
    
> [Collecter plus d’informations et pour obtenir une assistance supplémentaire](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)
    
## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Rechercher les causes courantes de Skype pour les erreurs de connexion Business en ligne
<a name="toc323194094"> </a>

La plupart des problèmes de connexion peuvent être suivies pour un petit nombre de causes, et plusieurs d'entre eux sont faciles à corriger. Le tableau ci-dessous répertorie certaines des causes des erreurs de connexion et des étapes que vous ou les utilisateurs peuvent prendre pour les résoudre.
  
|**Causes possibles**|**Résolution**|
|:-----|:-----|
|Lors de l’authentification, une boîte de dialogue s’affiche qui contient le membre de phrase suivant : **ne peut pas vérifier que le serveur est approuvé pour votre adresse de connexion. Quand même vous connecter ?** <br/> |Vérifiez que le nom de domaine dans la boîte de dialogue est un serveur de confiance dans votre organisation, par exemple, **domainName.contoso.com**. Demandez à l’utilisateur de sélectionner la case à cocher **toujours faire confiance à ce serveur** , puis cliquez sur **se connecter**. <br/> Les clients d’entreprise peuvent empêcher ce message lorsqu’un utilisateur se connecte pour la première fois en modifiant le Registre Windows sur l’ordinateur de chaque utilisateur. Pour plus d’informations, reportez-vous à la section [TrustModelData de modifier les clés de Registre](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
|Adresse de connexion a été correctement orthographiée, nom d’utilisateur ou mot de passe  <br/> | Vérifiez que le nom d’utilisateur et le mot de passe de l’utilisateur sont corrects. <br/>  Vérifiez que le nom de connexion de l’utilisateur est formaté comme suit : **bobk@contoso.com**. Cela peut être différent du format que vous utilisez pour vous connecter au réseau de votre organisation.  <br/>  Demandez à l’utilisateur de réessayer de vous connecter. <br/> |
|Mot de passe oublié  <br/> |Réinitialiser le mot de passe de l’utilisateur et l’informer du nouveau mot de passe temporaire.  <br/> |
|Pas de licence pour utiliser Skype pour professionnels en ligne  <br/> |Vérifiez que l’utilisateur est enregistré sous la forme d’un Skype pour des utilisateurs professionnels en ligne. Si ce n’est pas le cas, inscrire l’utilisateur et puis lui demander de vous connecter à nouveau.  <br/> |
|Mauvaise version de Skype pour Business Online installé  <br/> |Ce problème est généralement associé à un message d’erreur qui contient le membre de phrase suivant : **le service d’authentification peut être incompatible avec cette version du programme**.  <br/> Demandez à l’utilisateur pour désinstaller et réinstaller Skype pour entreprise en ligne à partir du portail d’Office 365.  <br/> |
|Problème d’acquérir un certificat personnel qui est nécessaire pour ouvrir une session  <br/> |Si l’adresse de connexion de l’utilisateur a récemment modifié, il faudra supprimer les données de connexion mises en cache. Demandez aux utilisateurs de se déconnecter, cliquez sur Supprimer mes informations de connexion à lier sur l’écran de connexion, puis essayez à nouveau.  <br/> |
|Permet de paramétrer un nom de domaine personnalisé, et les modifications ne peuvent pas ont été propagées via le système.  <br/> |Tout d’abord, assurez-vous que vous avez modifié les enregistrements de nom de domaine DNS (Domain Name Service) pour refléter la modification.  <br/> Si vous avez déjà apporté les modifications nécessaires de DNS, informez l’utilisateur d’essayer de connecter plus tard. Modifications DNS peuvent prendre jusqu'à 72 heures d’être répercutées dans tout le système.  <br/> |
|Système d’horloge plus synchronisée avec l’horloge du serveur  <br/> |Assurez-vous que le contrôleur de domaine de votre réseau est en cours de synchronisation avec une source de temps externe fiable. Pour plus d’informations, consultez l’article 816042 de la Base de connaissances [Comment faire pour configurer un serveur de temps faisant autorité dans Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/> |
   
Pour résoudre les problèmes de Skype pour les erreurs de connexion en ligne Business, démarrez en éliminant les causes les plus courantes de difficultés de connexion. Si nécessaire, vous pouvez alors suivre les étapes en fonction du type d’erreur de résolution spécifique. Si l’utilisateur ne peut pas toujours signer, collecter des informations supplémentaires et ensuite pour obtenir une assistance supplémentaire. 
  
## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Suivez les étapes de résolution d’une erreur spécifique (Enterprise seulement)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Ces instructions sont destinées principalement aux clients de Microsoft Office 365 Plan E. Si vous êtes un client P de Plan Office 365, passez à la section suivante,[collecter plus d’informations et pour obtenir une assistance supplémentaire ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information). 
  
Si l’utilisateur ne peut pas vous connecter après avoir essayé les suggestions dans la section précédente, vous pouvez ensuite effectuer un dépannage supplémentaire en fonction du type d’erreur. Le tableau ci-dessous répertorie les messages d’erreur les plus courants et les causes possibles. Le tableau suivant est des procédures détaillées pour résoudre chaque problème.
  
|**Message d’erreur**|**Causes possibles**|**Résolution**|
|:-----|:-----|:-----|
|Adresse de connexion introuvable  <br/> |Demandes de connexion à partir de l’Assistant Microsoft Online Services-ouverture de session (msoidsvc.exe) ne vont pas par l’intermédiaire de votre serveur proxy ou pare-feu externe.  <br/> |[Ajouter une entrée de pare-feu pour msoidsvc.exe à votre serveur proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Serveur est temporairement indisponible  <br/> |Si votre organisation possède un domaine personnalisé, les paramètres de système de nom de domaine (DNS) nécessaire est peut-être manquant ou incorrect.  <br/> |[Mettre à jour les paramètres DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Serveur est temporairement indisponible  <br/> |Si votre organisation utilise une ouverture de session unique avec Active Directory Federation Services (ADFS), vous avez peut-être utilisé un certificat auto-signé de Secure Socket Layer (SSL) plutôt que par une autorité de certification tierce.  <br/> |[Installer un certificat SSL de tiers sur votre serveur ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problème d’acquérir un certificat personnel qui est nécessaire pour ouvrir une session  <br/> |Si vous avez déjà supprimé les données mises en cache server utilisé pour vous connecter et l’erreur continue à apparaître, informations d’identification de sécurité de l’utilisateur est peut-être endommagées ou peut bloquer un dossier RSA sur l’ordinateur de l’utilisateur d’authentification.  <br/> |[Mettre à jour les informations d’identification de sécurité](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Une boîte de dialogue de confiance certificat s’affiche lorsqu’un utilisateur se connecte pour la première fois.  <br/> |Cette boîte de dialogue s’affiche si votre Skype pour Business server n’est pas encore répertorié dans la clé de Registre **TrustModelData** . <br/> |[Modifier des clés de Registre TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|L’utilisateur n’est pas activé SIP  <br/> |Si votre organisation a une installation précédente de Microsoft Office Communications Server ou de Microsoft Lync Server 2010, vous a ne peut-être pas supprimé vos utilisateurs à partir du serveur avant de le désactiver. Par conséquent, l’attribut **msRTCSIP-UserEnabled** a toujours la valeur **FALSE** dans les Services de domaine Active Directory. <br/> |[Mettre à jour les paramètres de l’utilisateur dans Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |
   
### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Ajouter une entrée de pare-feu pour msoidsvc.exe à votre serveur proxy
<a name="add-a-firewall"> </a>

Cette procédure est possible pour le message d’erreur suivant : **adresse de connexion introuvable**.
  
 **Remarque**: les étapes suivantes supposent que vous utilisez Microsoft Forefront Threat Management Gateway (TMG) 2010. Si vous disposez d’une solution de passerelle web différent, utilisez les paramètres décrits à l’étape 4 ci-dessous.
  
Pour créer une entrée d’application pour Msoidsvc.exe dans Forefront TMG 2010, procédez comme suit :
  
1. Dans le volet de gauche de Forefront, cliquez sur **réseau**.
    
2. Cliquez sur l’onglet **réseau** . Sous l’onglet **tâches** dans le volet droit, cliquez sur **Configurer les paramètres de Client Forefront TMG**.
    
3. Dans la boîte de dialogue **Paramètres du Client Forefront TMG** , cliquez sur **Nouveau**.
    
4. Dans la boîte de dialogue **Entrée de paramètre d’Application** , configurez les règles suivantes :
    
|**Application**|**Clé**|**Valeur**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Désactiver  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Pour plus d’informations, consultez l’article de la Base de connaissances Microsoft 2409256, [qu'impossible de se connecter sur Skype pour Business Online parce qu’un pare-feu local bloque la connexion](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### <a name="update-dns-settings"></a>Mettre à jour les paramètres DNS
<a name="update-dns-service"> </a>

Si votre organisation possède un domaine personnalisé, cette procédure est un correctif possible pour le message d’erreur suivant : **serveur est temporairement indisponible**.
  
- Pour plus d’informations sur la façon d’ajouter l’enregistrement CNAME suivant à votre domaine, contactez votre registraire de nom de domaine :
    
  - **Type d’enregistrement DNS**: CNAME 
    
  - **Nom**: sip
    
  - **Valeur/Destination**: sipdir.online.microsoft.com
    
Pour plus d’informations, consultez la Base de connaissances Microsoft l’article 2566790, [Skype de dépannage pour les problèmes de configuration DNS en ligne de Business dans Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).
  
### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Installer un certificat SSL de tiers sur votre serveur ADFS
<a name="verify-upn-and"> </a>

Pour installer un certificat SSL de tiers sur votre serveur Active domaine Federation Services (ADFS), procédez comme suit :
  
1. Obtenir un certificat SSL auprès d’une autorité de certification de tierce partie telle que VeriSign ou Thawte.
    
2. Installer le certificat sur votre serveur ADFS à l’aide de la console de gestion d’ADFS. 
    
### <a name="update-security-credentials"></a>Mettre à jour les informations d’identification de sécurité
<a name="update-security-credentials"> </a>

Cette procédure est possible pour le message d’erreur **problème acquérir un certificat personnel requis pour vous connecter**.
  
Pour éliminer les éventuels problèmes de certificat ou des informations d’identification, tout d’abord de renouveler le certificat de l’utilisateur dans le Gestionnaire de certificats Windows. Pour ce faire, procédez comme suit :
  
1. Ouvrez le Gestionnaire de certificat de Windows. Pour ce faire, cliquez sur **Démarrer**, sur **exécuter**, tapez **certmgr.msc**, puis cliquez sur **OK**. 
    
2. Double-cliquez sur **personnel**, puis double-cliquez sur **certificats**. 
    
3. Tri par la colonne **Délivré par** et puis recherchez un certificat qui est émis par le serveur de Communications.
    
4. Cliquez sur le certificat, puis cliquez sur **Supprimer**. 
    
Ensuite, si l’utilisateur exécute Windows 7, supprimez les informations d’identification stockées dans le Gestionnaire d’informations d’identification Windows. Pour ce faire, procédez comme suit :
  
1. Cliquez sur **Démarrer**, cliquez sur **Panneau de configuration**, puis cliquez sur **Gestionnaire d’informations d’identification**. 
    
2. Localisez le jeu d’informations d’identification qui est utilisé pour se connecter à Skype pour entreprise en ligne. 
    
3. Développez le jeu d’informations d’identification, puis cliquez sur **Supprimer du coffre**. 
    
4. Connectez-vous de nouveau et entrez à nouveau les informations d’identification de l’utilisateur.
    
Enfin, si l’utilisateur toujours Impossible de se connecter une fois que vous avez mis à jour leurs informations d’identification, essayez de supprimer le dossier RSA de l’ordinateur de l’utilisateur, car il bloque peut-être l’achèvement du processus d’authentification utilisateur :
  
1. Connectez-vous à l’ordinateur de l’utilisateur à l’aide d’un compte d’administrateur.
    
2. Si nécessaire, activez l’option d’affichage de dossier **Afficher les fichiers cachés**. 
    
3. Tapez la commande suivante dans la barre d’adresse de fichier Explorer : **C:\\Documents et paramètres\\nom d’utilisateur\\les données d’Application\\Microsoft\\Crypto\\RSA**, où ***nom_utilisateur*** est votre nom d’utilisateur Windows.
    
4. Supprimez tout dossier qui commence par le nom **S-1-5-21 -** suivie d’une chaîne de nombres.
    
### <a name="modify-trustmodeldata-registry-keys"></a>Modifier des clés de Registre TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Lorsqu’un utilisateur se connecte pour la première fois, ils peuvent recevoir une boîte de dialogue qui contient les éléments suivants : **ne peut pas vérifier que le serveur est approuvé pour votre adresse de connexion. Quand même vous connecter ?** Il s’agit d’une fonctionnalité de sécurité et non une erreur. Toutefois, vous pouvez empêcher la boîte de dialogue à l’aide d’un objet de stratégie de groupe (GPO) pour mettre à jour les ordinateurs des utilisateurs avec votre nom de domaine avant de les connectent pour la première fois. Pour ce faire, effectuez les opérations suivantes :
  
- Créer et déployer un objet de stratégie de groupe qui ajoute votre Skype pour nom de domaine d’entreprise — par exemple, domainName.contoso.com—to la valeur actuelle de HKEY_LOCAL_MACHINE\\Software\\stratégies\\Microsoft\\Communicator\\ TrustModelData.
    
> [!IMPORTANT]
>  Vous devez *Ajouter* votre nom de domaine à la valeur existante, pas simplement le remplacer.
  
Pour plus d’informations, consultez l’article de la Base de connaissances Microsoft 2531068, [que Skype pour les entreprises (Lync) ne peut pas vérifier que le serveur est approuvé pour votre adresse de connexion](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### <a name="update-user-settings-in-active-directory"></a>Mise à jour des paramètres utilisateur dans Active Directory
<a name="update-user-settings"> </a>

Si votre organisation a une installation précédente de Microsoft Office Communications Server ou de Microsoft Lync Server 2010, vous a ne peut-être pas supprimé vos utilisateurs à partir du serveur avant de le désactiver. Par conséquent, l’attribut **msRTCSIP-UserEnabled** a toujours la valeur **FALSE** dans les Services de domaine Active Directory.
  
Pour résoudre ce problème, procédez comme suit :
  
1. Mettre à jour l’attribut **msRTCSIP-UserEnabled** pour tous les utilisateurs affectés à **TRUE**.
    
2. Exécutez à nouveau le Microsoft Online Services-Outil de synchronisation d'annuaires (DirSync). Pour plus d’informations, consultez [AIntegrate vos locaux de répertoires avec Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx). 
    
Pour résoudre les problèmes de Skype pour les erreurs de connexion en ligne Business, démarrez en éliminant les causes les plus courantes de difficultés de connexion. Si nécessaire, vous pouvez alors suivre les étapes en fonction du type d’erreur de résolution spécifique. Si l’utilisateur ne peut pas toujours signer, collecter des informations supplémentaires et ensuite pour obtenir une assistance supplémentaire. 
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Utiliser le guide de dépannage de Support de Microsoft
<a name="toc325626447"> </a>

Si vous n’êtes toujours pas en mesure de résoudre des problèmes de connexion de l’utilisateur, consultez les suggestions dans la Base de connaissances Microsoft l’article 2541980, [Comment faire pour résoudre les problèmes de connexion dans Skype pour l’activité en ligne](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## <a name="collect-more-information-and-seek-additional-help"></a>Collecter plus d’informations et pour obtenir une assistance supplémentaire
<a name="collect-more-information"> </a>

Si vous avez suivi les instructions ci-dessus et que vous pouvez toujours pas résoudre vos problèmes de connexion, vous devez collecter des informations supplémentaires et contactez le support technique. Pour ce faire, procédez comme suit : 
  
1. Obtenir les fichiers journaux et les détails du journal des événements de Windows à partir de l’ordinateur de l’utilisateur. Pour obtenir des instructions détaillées, consultez la rubrique d’aide pour l’utilisateur final [Activer les journaux d’erreurs dans Lync](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).
    
2. Envoyer les fichiers journaux et des informations détaillées sur l’erreur au support technique de Microsoft.
    
Vous pouvez être invité à fournir des informations de Diagnostics supplémentaires en installant le Diagnostic de Microsoft Online Services et Shared Computer Toolkit de prise en charge de journalisation (MOSDAL) sur l’ordinateur de l’utilisateur affecté. Pour plus d’informations, reportez-vous [à l’aide de la Shared Computer Toolkit de prise en charge MOSDAL](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).
  
Pour résoudre les problèmes de Skype pour les erreurs de connexion en ligne Business, démarrez en éliminant les causes les plus courantes de difficultés de connexion. Si nécessaire, vous pouvez alors suivre les étapes en fonction du type d’erreur de résolution spécifique. Si l’utilisateur ne peut pas toujours signer, collecter des informations supplémentaires et ensuite pour obtenir une assistance supplémentaire. 
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Permettent d’ajouter des contacts de Skype Skype pour les utilisateurs professionnels](let-skype-for-business-users-add-skype-contacts.md)
