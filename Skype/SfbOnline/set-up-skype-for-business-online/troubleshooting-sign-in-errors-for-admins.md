---
title: Dépannage Skype pour les erreurs de connexion Business Online pour les administrateurs
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Découvrez les causes fréquentes de Skype pour Business Online pour les erreurs de connexion et de travail par le biais de ces problèmes. '
ms.openlocfilehash: 63bcd69fa4db2266647960c119c198797c154f75
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850212"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Dépannage Skype pour les erreurs de connexion Business Online pour les administrateurs

Pour résoudre les Skype pour les erreurs de connexion en ligne Business, démarrez en éliminant les causes les plus courantes des difficultés de connexion. Si nécessaire, vous pouvez alors suivre les étapes en fonction du type d’erreur de résolution spécifique. Si l’utilisateur toujours ne peut pas se connecter, recueillir des informations supplémentaires, puis demander une assistance supplémentaire.

## <a name="what-do-you-want-to-do"></a>Que voulez-vous faire ?
<a name="top"> </a>

> [Rechercher les causes fréquentes de Skype pour les erreurs de connexion Business en ligne](troubleshooting-sign-in-errors-for-admins.md#toc323194094)

> [Suivez les étapes de résolution d’une erreur spécifique (Enterprise uniquement)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)

> [Ajouter une entrée de pare-feu pour msoidsvc.exe à votre serveur proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)

> [Mettre à jour les paramètres DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)

> [Installer un certificat SSL de tiers sur votre serveur AD FS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)

> [Mettre à jour les informations d’identification de sécurité](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)

> [Modifier les clés de Registre TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)

> [Mise à jour des paramètres utilisateur dans Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)

> [Utiliser le guide de dépannage du Support de Microsoft](troubleshooting-sign-in-errors-for-admins.md#toc325626447)

> [Recueillir plus d’informations et pour obtenir une assistance supplémentaire](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Rechercher les causes fréquentes de Skype pour les erreurs de connexion Business en ligne
<a name="toc323194094"> </a>

La plupart des problèmes de connexion peuvent être suivis pour un petit nombre de causes et la plupart de ces sont faciles à corriger. Le tableau ci-dessous répertorie certaines causes courantes des erreurs de connexion et certaines étapes que vous ou les utilisateurs peuvent suivre pour les résoudre.

|**Cause possible**|**Résolution**|
|:-----|:-----|
|Lors de la connexion, une boîte de dialogue qui contient l’expression suivante apparaît : **ne peut pas vérifier que le serveur est approuvé pour votre adresse de connexion. Quand même vous connecter ?** <br/> |Vérifiez que le nom de domaine dans la boîte de dialogue est un serveur approuvé dans votre organisation, par exemple, **domainName.contoso.com**. Demandez à l’utilisateur pour sélectionner la case à cocher **toujours faire confiance à ce serveur** , puis cliquez sur **se connecter**. <br/> Les clients d’entreprise peuvent empêcher ce message lorsqu’un utilisateur se connecte pour la première fois en modifiant le Registre Windows sur l’ordinateur de chaque utilisateur. Pour plus d’informations, voir [TrustModelData modifier les clés de Registre](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
|Adresse de connexion faute de frappe, nom d’utilisateur ou mot de passe  <br/> | Vérifiez que le nom d’utilisateur et mot de passe de l’utilisateur sont correctes. <br/>  Vérifiez que le nom de connexion de l’utilisateur est formaté comme suit : **bobk@contoso.com**. Cela peut être différent du format que vous utilisez pour vous connecter au réseau de votre organisation.  <br/>  Demandez à l’utilisateur de réessayer de vous connecter. <br/> |
|Mot de passe oublié  <br/> |Réinitialiser le mot de passe et informer du nouveau mot de passe temporaire.  <br/> |
|Pas de licence pour utiliser Skype pour Business en ligne  <br/> |Vérifiez que l’utilisateur est enregistré en tant qu’un Skype pour l’utilisateur d’entreprise en ligne. Dans le cas contraire, enregistrer l’utilisateur, puis lui demander à vous reconnecter.  <br/> |
|Skype pour Business Online installé une version incorrecte  <br/> |Ce problème est généralement associé à un message d’erreur qui contient l’expression suivante : **le service d’authentification peut être incompatible avec cette version du programme**.  <br/> Demandez à l’utilisateur pour désinstaller et réinstaller Skype pour Business Online à partir du portail Office 365.  <br/> |
|Problème d’acquisition d’un certificat personnel est requis pour se connecter  <br/> |Si l’adresse de connexion de l’utilisateur a récemment modifié, il faudra supprimer les données de connexion mises en cache. Demandez aux utilisateurs de se déconnecter, cliquez sur Supprimer mes informations de connexion lier sur l’écran de connexion, puis réessayez.  <br/> |
|Définir un nom de domaine personnalisé et les modifications ne peuvent pas fini de se propager dans le système.  <br/> |Tout d’abord, assurez-vous que vous avez modifié les enregistrements de nom de domaine DNS (Domain Name Service) pour refléter les modifications.  <br/> Si vous avez déjà apporté les modifications DNS nécessaires, informer l’utilisateur à essayez de vous connecter ultérieurement. Les modifications DNS peuvent prendre jusqu'à 72 heures pour être répercutées dans le système.  <br/> |
|Système d’horloge pas synchronisé avec l’horloge du serveur  <br/> |Assurez-vous que le contrôleur de domaine de votre réseau est en cours de synchronisation avec une source externe fiable. Pour plus d’informations, consultez l’article 816042 de la Base de connaissances Microsoft [Comment faire pour configurer un serveur de temps faisant autorité dans Windows Server](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/> |

Pour résoudre les Skype pour les erreurs de connexion en ligne Business, démarrez en éliminant les causes les plus courantes des difficultés de connexion. Si nécessaire, vous pouvez alors suivre les étapes en fonction du type d’erreur de résolution spécifique. Si l’utilisateur toujours ne peut pas se connecter, recueillir des informations supplémentaires, puis demander une assistance supplémentaire.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Suivez les étapes de résolution d’une erreur spécifique (Enterprise uniquement)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Ces instructions sont destinées principalement aux clients Microsoft Office 365 planifier E. Si vous êtes un client Office 365 planifier P, passez à la section suivante,[recueillir plus d’informations et pour obtenir une assistance supplémentaire ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).

Si l’utilisateur ne peut pas se connecter une fois que vous avez essayé les suggestions dans la section précédente, vous pouvez effectuer des opérations de dépannage en fonction du type d’erreur. Le tableau ci-dessous répertorie les messages d’erreur les plus courants et causes possibles. Le tableau suivant est des procédures détaillées pour chaque problème.

|**Message d’erreur**|**Cause possible**|**Résolution**|
|:-----|:-----|:-----|
|Adresse de connexion introuvable  <br/> |Demandes de connexion à partir de l’Assistant Microsoft Online Services Sign-On (msoidsvc.exe) ne sont pas passer par votre pare-feu externe ou un serveur proxy.  <br/> |[Ajouter une entrée de pare-feu pour msoidsvc.exe à votre serveur proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Server est temporairement non disponible  <br/> |Si votre organisation a un domaine personnalisé, les paramètres de nom de domaine DNS (Domain Name System) requis est peut-être manquant ou incorrect.  <br/> |[Mettre à jour les paramètres DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Server est temporairement non disponible  <br/> |Si votre organisation est à l’aide de l’authentification unique avec Active Directory Federation Services (ADFS), vous avez peut-être utilisé un certificat auto-signé de Secure Sockets Layer (SSL) plutôt qu’à partir d’une autorité de certification tierce.  <br/> |[Installer un certificat SSL de tiers sur votre serveur AD FS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problème d’acquisition d’un certificat personnel est requis pour se connecter  <br/> |Si vous avez déjà supprimé les données du serveur de mise en cache utilisé pour la connexion et l’erreur continue à apparaître, informations d’identification de sécurité de l’utilisateur est endommagées, ou un dossier RSA sur l’ordinateur de l’utilisateur peut bloquer l’authentification.  <br/> |[Mettre à jour les informations d’identification de sécurité](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Une boîte de dialogue certificat confiance s’affiche lorsqu’un utilisateur se connecte pour la première fois.  <br/> |Cette boîte de dialogue s’affiche si votre Skype pour Business server n’est pas encore répertorié dans la clé de Registre **TrustModelData** . <br/> |[Modifier les clés de Registre TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|L’utilisateur n’est pas activé SIP  <br/> |Si votre organisation a une installation précédente de Microsoft Office Communications Server ou Microsoft Lync Server 2010, vous a ne peut-être pas supprimé vos utilisateurs à partir du serveur avant de le désactiver. Par conséquent, l’attribut **msRTCSIP-UserEnabled** est toujours définie sur **FALSE** dans les Services de domaine Active Directory. <br/> |[Mise à jour des paramètres utilisateur dans Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Ajouter une entrée de pare-feu pour msoidsvc.exe à votre serveur proxy
<a name="add-a-firewall"> </a>

Cette procédure est un correctif pour le message d’erreur suivant : **adresse de connexion introuvable**.

> [!NOTE]
> Les étapes suivantes supposent que vous utilisez Microsoft Forefront Threat Management Gateway (TMG) 2010. Si vous disposez d’une solution de passerelle web différente, utilisez les paramètres décrits à l’étape 4 ci-dessous.


Pour créer une entrée d’application pour Msoidsvc.exe dans Forefront TMG 2010, procédez comme suit :

1. Dans le volet gauche de Forefront, cliquez sur **réseau**.

2. Cliquez sur l’onglet **réseau** . Sous l’onglet **tâches** dans le volet droit, cliquez sur **Configurer les paramètres du Client Forefront TMG**.

3. Dans la boîte de dialogue **Paramètres du Client Forefront TMG** , cliquez sur **Nouveau**.

4. Dans la boîte de dialogue **Paramètre entrée d’Application** , configurez les règles suivantes :

|**Application**|**Clé**|**Valeur**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Désactiver  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

Pour plus d’informations, voir l’article de la Base de connaissances Microsoft 2409256, [que vous ne pouvez pas vous connecter à Skype pour Business Online car un pare-feu local bloque la connexion](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).

### <a name="update-dns-settings"></a>Mettre à jour les paramètres DNS
<a name="update-dns-service"> </a>

Si votre organisation a un domaine personnalisé, cette procédure est un correctif pour le message d’erreur suivant : **Server est temporairement non disponible**.

- Pour plus d’informations sur la façon d’ajouter l’enregistrement CNAME suivant à votre domaine, contactez votre serveur d’inscriptions de nom de domaine :

  - **Type d’enregistrement DNS**: CNAME

  - **Nom**: sip

  - **Valeur/Destination**: sipdir.online.microsoft.com

Pour plus d’informations, voir l’article de la Base de connaissances Microsoft 2566790, [Skype de dépannage pour les problèmes de configuration DNS en ligne d’entreprise dans Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Installer un certificat SSL de tiers sur votre serveur AD FS
<a name="verify-upn-and"> </a>

Pour installer un certificat SSL de tiers sur votre serveur Active domaine Federation Services (ADFS), procédez comme suit :

1. Obtenir un certificat SSL auprès d’une autorité de certification tierce telles que VeriSign ou Thawte.

2. Installer le certificat sur votre serveur ADFS à l’aide de la console de gestion ADFS.

### <a name="update-security-credentials"></a>Mettre à jour les informations d’identification de sécurité
<a name="update-security-credentials"> </a>

Cette procédure est un correctif pour le message d’erreur **problème l’acquisition d’un certificat personnel requis pour vous connecter**.

Pour éliminer les éventuels problèmes de certificat ou des informations d’identification, tout d’abord renouveler le certificat de l’utilisateur dans le Gestionnaire de certificats Windows. Pour ce faire, procédez comme suit :

1. Ouvrez le Gestionnaire de certificats Windows. Pour ce faire, cliquez sur **Démarrer**, sur **exécuter**, tapez **certmgr.msc**, puis cliquez sur **OK**.

2. Double-cliquez sur **personnel**, puis double-cliquez sur **certificats**.

3. Tri par la colonne **Délivré par** , puis recherchez un certificat émis par Communications Server.

4. Cliquez sur le certificat, puis cliquez sur **Supprimer**.

Ensuite, si l’utilisateur exécute Windows 7, supprimer leurs informations d’identification stockées dans le Gestionnaire d’informations d’identification Windows. Pour ce faire, procédez comme suit :

1. Cliquez sur **Démarrer**, cliquez sur **Le panneau de configuration**, puis cliquez sur **Gestionnaire d’informations d’identification**.

2. Localisez le jeu d’informations d’identification qui est utilisé pour se connecter à Skype pour Business Online.

3. Développez le jeu d’informations d’identification, puis cliquez sur **Supprimer de coffre-fort**.

4. Se reconnecter et entrez à nouveau les informations d’identification de l’utilisateur.

Enfin, si l’utilisateur toujours ne peut pas se connecter une fois que vous avez mis à jour leurs informations d’identification, essayez de supprimer le dossier RSA sur l’ordinateur de l’utilisateur, car il pourrait bloquer la fin du processus d’authentification utilisateur :

1. Connectez-vous à l’ordinateur de l’utilisateur à l’aide d’un compte d’administrateur.

2. Si nécessaire, activez l’option d’affichage dossier **fichiers cachés**.

3. Tapez ce qui suit dans la barre d’adresse de fichier Explorer : **C:\\Documents and Settings\\UserName\\les données d’Application\\Microsoft\\chiffrement\\RSA**, où ***nom_utilisateur*** est votre nom d’utilisateur Windows.

4. Supprimer n’importe quel dossier qui commence par le nom **S-1-5-21 -** suivi d’une chaîne de nombres.

### <a name="modify-trustmodeldata-registry-keys"></a>Modifier les clés de Registre TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Lorsqu’un utilisateur se connecte pour la première fois, ils peuvent recevoir une boîte de dialogue qui contient les éléments suivants : **ne peut pas vérifier que le serveur est approuvé pour votre adresse de connexion. Quand même vous connecter ?** Il s’agit d’une fonctionnalité de sécurité et non une erreur. Toutefois, vous pouvez empêcher la boîte de dialogue à l’aide d’un objet de stratégie de groupe (GPO) pour mettre à jour les ordinateurs des utilisateurs avec votre nom de domaine avant de connecter pour la première fois. Pour ce faire, procédez comme suit :

- Créer et déployer une stratégie de groupe qui ajoute votre Skype pour le nom de domaine d’entreprise — par exemple, domainName.contoso.com—to la valeur actuelle de HKEY_LOCAL_MACHINE\\logiciel\\stratégies\\Microsoft\\Communicator\\ TrustModelData.

> [!IMPORTANT]
>  Vous devez *Ajouter* votre nom de domaine à la valeur existante, pas simplement la remplacer.

Pour plus d’informations, voir l’article de la Base de connaissances Microsoft 2531068, [que Skype pour les entreprises (Lync) ne peut pas vérifier que le serveur est approuvé pour votre adresse de connexion](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).

### <a name="update-user-settings-in-active-directory"></a>Mise à jour des paramètres utilisateur dans Active Directory
<a name="update-user-settings"> </a>

Si votre organisation a une installation précédente de Microsoft Office Communications Server ou Microsoft Lync Server 2010, vous a ne peut-être pas supprimé vos utilisateurs à partir du serveur avant de le désactiver. Par conséquent, l’attribut **msRTCSIP-UserEnabled** est toujours définie sur **FALSE** dans les Services de domaine Active Directory.

Pour résoudre ce problème, procédez comme suit :

1. Mettre à jour l’attribut **msRTCSIP-UserEnabled** pour tous les utilisateurs affectés à **la valeur TRUE**.

2. Réexécutez l’outil de synchronisation de répertoire Microsoft Online Services (DirSync). Pour plus d’informations, consultez [AIntegrate votre site de répertoires avec Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).

Pour résoudre les Skype pour les erreurs de connexion en ligne Business, démarrez en éliminant les causes les plus courantes des difficultés de connexion. Si nécessaire, vous pouvez alors suivre les étapes en fonction du type d’erreur de résolution spécifique. Si l’utilisateur toujours ne peut pas se connecter, recueillir des informations supplémentaires, puis demander une assistance supplémentaire.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Utiliser le guide de dépannage du Support de Microsoft
<a name="toc325626447"> </a>

Si vous n’êtes toujours pas en mesure de résoudre les problèmes de connexion de l’utilisateur, passez en revue les suggestions proposées dans l’article de la Base de connaissances Microsoft 2541980, [comment résoudre les problèmes de connexion dans Skype pour Business Online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).

## <a name="collect-more-information-and-seek-additional-help"></a>Recueillir plus d’informations et pour obtenir une assistance supplémentaire
<a name="collect-more-information"> </a>

Si vous avez suivi les instructions ci-dessus et toujours ne peut pas résoudre vos problèmes de connexion, vous devez recueillir des informations supplémentaires et contactez le support technique. Pour ce faire, procédez comme suit :

1. Obtenir les fichiers journaux et les détails du journal des événements Windows à partir de l’ordinateur de l’utilisateur. Pour obtenir des instructions pas à pas, consultez la rubrique d’aide pour l’utilisateur final [Activer les journaux d’erreurs dans Lync](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).

2. Envoyer les fichiers journaux et des informations détaillées sur l’erreur au support technique Microsoft.

Vous pouvez être invité à fournir des informations de diagnostic supplémentaires en installant le Microsoft Online Services Diagnostics et journalisation () prise en charge MOSDAL sur l’ordinateur de l’utilisateur concerné. Pour plus d’informations, voir [l’aide de la prise en charge MOSDAL](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).

Pour résoudre les Skype pour les erreurs de connexion en ligne Business, démarrez en éliminant les causes les plus courantes des difficultés de connexion. Si nécessaire, vous pouvez alors suivre les étapes en fonction du type d’erreur de résolution spécifique. Si l’utilisateur toujours ne peut pas se connecter, recueillir des informations supplémentaires, puis demander une assistance supplémentaire.

## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)


