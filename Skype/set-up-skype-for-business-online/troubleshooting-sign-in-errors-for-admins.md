---
title: "Résolution des erreurs de connexion à Skype Entreprise Online pour les administrateurs"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
description: "Learn common causes for Skype for Business Online sign-errors and Work through troubleshooting these problems. "
---

# Résolution des erreurs de connexion à Skype Entreprise Online pour les administrateurs

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1). 
  
Pour résoudre les erreurs de connexion Skype Entreprise Online, commencez en supprimant les causes les plus courantes de connexion difficulté. Si nécessaire, vous pouvez suivre puis résolution spécifique étapes basées sur le type d'erreur. Si l'utilisateur toujours pas vous connecter, collecter des informations supplémentaires et rechercher une aide supplémentaire.
  
## Que voulez-vous faire ?
<a name="__top"> </a>

> [Vérifier les causes courantes des erreurs de connexion Skype Entreprise Online](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc323194094)
    
> [Suivre la procédure de résolution d'une erreur spécifique (Entreprise seulement)](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626440)
    
> [Ajouter une entrée de pare-feu pour msoidsvc.exe au serveur proxy](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall)
    
> [Mettre à jour les paramètres DNS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service)
    
> [Installer un certificat SSL tiers sur le serveur ADFS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and)
    
> [Mettre à jour les informations d'identification de sécurité](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1)
    
> [Modifier les clés du Registre TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)
    
> [Mettre à jour les paramètres d'utilisateur dans Active Directory](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1)
    
> [Utilisation du guide de dépannage du Support Microsoft](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626447)
    
> [Recueillir d'autres informations et rechercher de l'aide supplémentaire](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)
    
## Vérifier les causes courantes des erreurs de connexion Skype Entreprise Online
<a name="__toc323194094"> </a>

Permet de suivre la plupart des problèmes de connexion à un petit nombre de causes, et la plupart d'entre elles sont faciles à corriger. Le tableau ci-dessous répertorie quelques causes courantes des erreurs de connexion et certaines étapes vous ou les utilisateurs pour les résoudre.
  
|**Cause possible**|**Résolution**|
|:-----|:-----|
|Au cours de connexion, une boîte de dialogue s'affiche qui contient la phrase suivante : **ne peut pas vérifier que le serveur est fiable pour votre adresse de connexion. Quand même vous connecter ?** <br/> |Vérifiez que le nom de domaine indiqué dans la boîte de dialogue est un serveur approuvé dans votre organisation, par exemple, **NomDomaine.contoso.com**. Demandez à l'utilisateur de cocher la case **Toujours faire confiance à ce serveur**, puis de cliquer sur **Connexion**. <br/> Les clients Entreprise peuvent éviter que ce message s'affiche lorsqu'un utilisateur se connecte pour la première fois en modifiant le Registre Windows sur l'ordinateur de chaque utilisateur. Pour plus de détails, consultez la rubrique [Modifier les clés du Registre TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry).  <br/> |
|Adresse de connexion, nom d'utilisateur ou mot de passe incorrectement entrés  <br/> | Vérifiez que le nom d'utilisateur et le mot de passe de l'utilisateur sont corrects. <br/>  Vérifiez que le nom d'utilisateur est au format : **bobk@contoso.com**. Ce format peut être différent de celui utilisé lors de la connexion au réseau de votre organisation.  <br/>  Demandez à l'utilisateur de réessayer de se connecter à nouveau. <br/> |
|Mot de passe oublié  <br/> |Réinitialisez le mot de passe de l'utilisateur et fournissez-lui son nouveau mot de passe temporaire.  <br/> |
|Pas de licence pour utiliser Skype Entreprise Online  <br/> |Vérifiez que l'utilisateur est enregistré en tant qu'un utilisateur Skype Entreprise Online. Dans le cas contraire, enregistrer l'utilisateur et puis demandez-lui de vous reconnecter.  <br/> |
|Version incorrecte de Skype Entreprise Online installé  <br/> |En règle générale, ce problème est associé à un message d'erreur contenant la phrase suivante : ** le service d'authentification n'est pas compatible avec cette version du programme**.  <br/> Demandez à l'utilisateur de désinstaller et réinstaller Skype Entreprise Online à partir du portail Office 365.  <br/> |
|Problème d'acquisition d'un certificat personnel requis pour établir la connexion  <br/> |Si l'adresse de connexion de l'utilisateur a changé récemment, il faudra supprimer les données de connexion mises en cache. Demandez aux utilisateurs de se déconnecter, cliquez sur Supprimer mes informations de connexion à lier dans l'écran de connexion, puis réessayez.  <br/> |
|Vous avez défini un nom de domaine personnalisé et les modifications n'ont peut-être pas fini de se propager dans le système  <br/> |Tout d'abord, assurez-vous que vous avez modifié les enregistrements de Service de nom de domaine (DNS) pour refléter les modifications.  <br/> Si vous avez déjà apporté les modifications DNS nécessaires, conseillez à l'utilisateur de se connecter ultérieurement. La prise en compte des modifications DNS dans le système peut prendre jusqu'à 72 heures.  <br/> |
|L'horloge système n'est pas synchronisée avec l'horloge du serveur  <br/> |Vérifiez que le contrôleur de domaine réseau est synchronisé avec une source de temps externe fiable. Pour plus d'informations, reportez-vous à l'article 816042 de la Base de connaissances Microsoft intitulé [Comment configurer un serveur de temps de référence dans Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).  <br/> |
   
[Cet article a été traduit automatiquement, voir l'avertissement. Vous pouvez consulter la version en anglais de cet article icihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Pour résoudre les erreurs de connexion Skype Entreprise Online, commencez en supprimant les causes les plus courantes de connexion difficulté. Si nécessaire, vous pouvez suivre puis résolution spécifique étapes basées sur le type d'erreur. Si l'utilisateur toujours pas vous connecter, collecter des informations supplémentaires et rechercher une aide supplémentaire.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Suivre la procédure de résolution d'une erreur spécifique (Entreprise seulement)
<a name="__toc325626440"> </a>

> [!IMPORTANT]
> Ces instructions sont fournies principalement à l'intention des clients Microsoft Office 365 Plan E. Si vous êtes un client Office 365 Plan P, passez à la section suivante[Recueillir d'autres informations et rechercher de l'aide supplémentaire](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1). 
  
Si l'utilisateur ne parvient pas à se connecter après l'application des suggestions de la section précédente, suivez les procédures de résolution selon les types d'erreur. Le tableau ci-après répertorie les messages d'erreur les plus courants et les causes possibles. Vous trouverez en dessous du tableau les procédures détaillées pour résoudre chaque problème.
  
|**Message d'erreur**|**Cause possible**|**Résolution**|
|:-----|:-----|:-----|
|Adresse de connexion introuvable  <br/> |Les demandes de connexion provenant de l'Assistant de connexion Microsoft Online Services (msoidsvc.exe) ne passent pas à travers le pare-feu externe ou le serveur proxy.  <br/> |[Ajouter une entrée de pare-feu pour msoidsvc.exe au serveur proxy](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall) <br/> |
|Le serveur est temporairement indisponible  <br/> |Si votre organisation possède un domaine personnalisé, les paramètres DNS (Domain Name System) nécessaires sont peut-être manquants ou incorrects.  <br/> |[Mettre à jour les paramètres DNS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service) <br/> |
|Le serveur est temporairement indisponible  <br/> |Si votre organisation utilise l'authentification unique avec les services ADFS (Active Directory Federation Services), il est possible que vous ayez eu recours à un certificat SSL (Secure Socket Layer) auto-signé au lieu d'un certificat provenant d'une autorité de certification tierce.  <br/> |[Installer un certificat SSL tiers sur le serveur ADFS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and) <br/> |
|Problème d'acquisition d'un certificat personnel requis pour établir la connexion  <br/> |Si vous avez déjà supprimé les données de serveur mises en cache utilisées pour se connecter et l'erreur continue à apparaître, informations d'identification de sécurité de l'utilisateur peuvent être corrompues ou un dossier RSA sur l'ordinateur de l'utilisateur peut bloquer l'authentification.  <br/> |[Mettre à jour les informations d'identification de sécurité](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1) <br/> |
|Une boîte de dialogue relative à l'approbation du certificat s'affiche lorsque l'utilisateur se connecte pour la première fois.  <br/> |Boîte de dialogue apparaît si votre serveur Skype Entreprise n'est pas encore répertorié sous la clé du Registre **TrustModelData**.  <br/> |[Modifier les clés du Registre TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry) <br/> |
|L'utilisateur n'est pas activé pour SIP  <br/> |Si votre organisation dispose d'une installation antérieure de Microsoft Office Communications Server ou de Microsoft Lync Server 2010, il est possible que vos utilisateurs n'aient pas été supprimés du serveur avant sa mise hors service. Dans ce cas, l'attribut **msRTCSIP-UserEnabled** sera toujours défini sur **FALSE** dans les services de domaine Active Directory. <br/> |[Mettre à jour les paramètres d'utilisateur dans Active Directory](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1) <br/> |
   
### Ajouter une entrée de pare-feu pour msoidsvc.exe au serveur proxy
<a name="__add_a_firewall"> </a>

Cette procédure peut résoudre l'erreur suivante : **Adresse de connexion introuvable**.
  
 **REMARQUE**: la procédure ci-après suppose que vous utilisez Microsoft Forefront Threat Management Gateway (TMG) 2010. Si vous avez recours à une autre solution de passerelle web, utilisez les paramètres décrits à l'étape 4 ci-après.
  
Pour créer une entrée d'application pour Msoidsvc.exe dans Forefront TMG 2010, procédez comme suit :
  
1. Dans le volet gauche de Forefront, cliquez sur **Réseau**.
    
2. Cliquez sur l'onglet **Réseau**. Sous l'onglet **Tâches** du volet droit, cliquez sur **Configurer les paramètres du client Forefront TMG**.
    
3. Dans la boîte de dialogue **Paramètres du client Forefront TMG**, cliquez sur **Nouveau**.
    
4. Dans la boîte de dialogue **Paramètre d'entrée de l'application**, configurez les règles suivantes :
    
|****Application****|****Clé****|****Valeur****|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Pour plus d'informations, voir l'article de la Base de connaissances Microsoft 2409256, [que vous ne pouvez pas vous connecter à Skype entreprise Online, car un pare-feu local bloque la connexion](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### Mettre à jour les paramètres DNS
<a name="__update_dns_service"> </a>

Si votre organisation possède un domaine personnalisé, cette procédure peut résoudre l'erreur suivante : **Le serveur est temporairement indisponible**.
  
- Contactez le bureau d'enregistrement de noms de domaine pour obtenir des informations sur l'ajout de l'enregistrement CNAME suivant à votre domaine :
    
  - **Type d'enregistrement DNS**: CNAME
    
  - **Nom**: sip
    
  - **Valeur/Destination**: sipdir.online.microsoft.com
    
Pour plus d'informations, voir l'article 2566790 de la Base de connaissances Microsoft, [Résolution des problèmes de Skype entreprise Online DNS les problèmes de configuration dans Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)et à l'article Wiki Office 365, [intitulé vérification du fonctionnement du réseau avec Skype entreprise (Lync) Online](https://go.microsoft.com/fwlink/?linkid=231156).
  
### Installer un certificat SSL tiers sur le serveur ADFS
<a name="__verify_upn_and"> </a>

Pour installer un certificat SSL tiers sur le serveur ADFS (Active Domain Federation Services), procédez comme suit :
  
1. Obtenez un certificat SSL auprès d'une autorité de certification tierce telle que VeriSign ou Thawte.
    
2. Installer le certificat sur le serveur ADFS à l'aide de la console de gestion des services ADFS.
    
### Mettre à jour les informations d'identification de sécurité
<a name="__update_security_credentials_1"> </a>

Cette procédure peut permettre de résoudre l'erreur suivante : **Un problème s'est produit lors de l'acquisition d'un certificat personnel requis pour établir la connexion**.
  
Pour éliminer les problèmes d'informations d'identification ou de certificats possibles, renouvelez d'abord le certificat de l'utilisateur dans le Gestionnaire de certificats Windows. Pour cela, procédez comme suit :
  
1. Ouvrez le Gestionnaire de certificats Windows. Pour cela, cliquez sur **Démarrer**, sur **Exécuter**, tapez **certmgr.msc**, puis cliquez sur **OK**.
    
2. Double-cliquez sur **Personnel**, puis sur **Certificats**.
    
3. Effectuez un tri selon la colonne **Délivré par**, puis recherchez un certificat émis par Communications Server.
    
4. Cliquez avec le bouton droit sur le certificat, puis cliquez sur **Supprimer**.
    
Si l'utilisateur exécute Windows 7, supprimez ensuite ces informations d'identification stockées dans le Gestionnaire d'informations d'identification Windows. Pour cela, procédez comme suit :
  
1. Cliquez sur **Démarrer**, sur **Panneau de configuration**, puis sur **Gestionnaire d'informations d'identification**.
    
2. Recherchez le jeu d'informations d'identification est utilisé pour vous connecter à Skype Entreprise en ligne.
    
3. Développez le jeu d'informations d'identification, puis cliquez sur **Supprimer de l'archivage sécurisé**.
    
4. Se connecter à nouveau et entrez à nouveau les informations d'identification de l'utilisateur.
    
Enfin, si l'utilisateur ne parvient toujours pas à se connecter après la mise à jour de ses informations d'identification, essayez de supprimer le dossier RSA sur l'ordinateur de l'utilisateur, car celui-ci peut empêcher l'achèvement du processus d'authentification utilisateur :
  
1. Connectez-vous à l'ordinateur de l'utilisateur à l'aide d'un compte d'administrateur.
    
2. Si nécessaire, activez l'option d'affichage dossier **Afficher les fichiers cachés**.
    
3. Tapez les informations suivantes dans la barre d'adresses de l'Explorateur de fichiers : **C:\\Documents and Settings\\NomUtilisateur\\Application Data\\Microsoft\\Crypto\\RSA**, où ** *NomUtilisateur* ** ** représente votre nom de connexion Windows**.
    
4. Supprimez tout dossier dont le nom commence par **S-1-5-21-**, suivi d'une chaîne de nombres.
    
### Modifier les clés du Registre TrustModelData
<a name="__modify_trustmodeldata_registry"> </a>

Lorsqu'un utilisateur se connecte pour la première fois, ils peuvent recevoir une boîte de dialogue qui contient les éléments suivants : **ne peut pas vérifier que le serveur est fiable pour votre adresse de connexion. Quand même vous connecter ?** Il s'agit d'une fonctionnalité de sécurité et non une erreur. Toutefois, vous pouvez empêcher la boîte de dialogue à l'aide d'un objet (stratégie de groupe) pour les ordinateurs des utilisateurs de mettre à jour avec votre nom de domaine avant qu'ils se connecter pour la première fois. Pour ce faire, procédez comme suit :
  
- Créez et déployez un objet de stratégie de groupe qui ajoute votre nom de domaine Skype Entreprise  par exemple, domainName.contoso.comto la valeur actuelle de HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.
    
> [!IMPORTANT]
> Vous devez  *ajouter*  votre nom de domaine à la valeur existante, pas simplement la remplacer.
  
Pour plus d'informations, reportez-vous à l'article 2531068 de la base de connaissances Microsoft, [Skype Entreprise (Lync) ne peut pas vérifier que le serveur est fiable pour votre adresse de connexion](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### Mettre à jour les paramètres d'utilisateur dans Active Directory
<a name="__update_user_settings_1"> </a>

Si votre organisation dispose d'une installation antérieure de Microsoft Office Communications Server ou de Microsoft Lync Server 2010, il est possible que vos utilisateurs n'aient pas été supprimés du serveur avant sa mise hors service. Dans ce cas, l'attribut **msRTCSIP-UserEnabled** sera toujours défini sur **FALSE** dans les services de domaine Active Directory.
  
Pour résoudre ce problème, procédez comme suit :
  
1. Mettez à jour l'attribut **msRTCSIP-UserEnabled** pour tous les utilisateurs affectés à **TRUE**.
    
2. Réexécutez l'outil de synchronisation Microsoft Online Services Directory (DirSync). Pour plus d'informations, voir [répertoires AIntegrate votre locales avec Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).
    
[Cet article a été traduit automatiquement, voir l'avertissement. Vous pouvez consulter la version en anglais de cet article icihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Pour résoudre les erreurs de connexion Skype Entreprise Online, commencez en supprimant les causes les plus courantes de connexion difficulté. Si nécessaire, vous pouvez suivre puis résolution spécifique étapes basées sur le type d'erreur. Si l'utilisateur toujours pas vous connecter, collecter des informations supplémentaires et rechercher une aide supplémentaire.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Utilisation du guide de dépannage du Support Microsoft
<a name="__toc325626447"> </a>

Si vous parvenez toujours pas à résoudre les problèmes de connexion de l'utilisateur, passez en revue les suggestions de la Base de connaissances Microsoft l'article 2541980, [comment résoudre les problèmes de connexion dans Skype entreprise Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## Recueillir d'autres informations et rechercher de l'aide supplémentaire
<a name="__collect_more_information_1"> </a>

Si vous avez suivi les recommandations ci-dessus et que vous pouvez toujours pas résoudre vos problèmes de connexion, vous devez collecter des informations supplémentaires et contactez le support technique. Pour ce faire, procédez comme suit :
  
1. Obtenir les fichiers journaux et les détails du journal des événements Windows à partir de l'ordinateur de l'utilisateur. Pour obtenir des instructions étape par étape, consultez la rubrique d'aide pour l'utilisateur final [Activation de la journalisation des erreurs dans Skype Entreprise (Lync)](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).
    
2. Envoyez les fichiers journaux et les informations détaillées sur l'erreur à l'équipe de support technique Microsoft.
    
Vous serez peut-être invité à fournir des informations de diagnostic supplémentaires en installant le Kit de ressources de support Microsoft Online Services Diagnostic and Logging (MOSDAL) sur l'ordinateur de l'utilisateur concerné par le problème. Pour plus d'informations, voir [Utilisation du Kit de ressources de support MOSDAL](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).
  
[Cet article a été traduit automatiquement, voir l'avertissement. Vous pouvez consulter la version en anglais de cet article icihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Pour résoudre les erreurs de connexion Skype Entreprise Online, commencez en supprimant les causes les plus courantes de connexion difficulté. Si nécessaire, vous pouvez suivre puis résolution spécifique étapes basées sur le type d'erreur. Si l'utilisateur toujours pas vous connecter, collecter des informations supplémentaires et rechercher une aide supplémentaire.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

