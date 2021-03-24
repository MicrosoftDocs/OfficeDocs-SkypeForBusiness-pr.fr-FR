---
title: Résolution des erreurs de connexion à Skype Entreprise Online pour les administrateurs
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Découvrez les causes courantes des erreurs de connexion à Skype Entreprise Online et résolvez-les. '
ms.openlocfilehash: ec441528fb6805f4c2c1c47c50f2debd62675a8a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103840"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Résolution des erreurs de connexion à Skype Entreprise Online pour les administrateurs

Pour résoudre les erreurs de connexion à Skype Entreprise Online, commencez par éliminer les causes les plus courantes des problèmes de connexion. Si nécessaire, vous pouvez suivre des étapes de résolution spécifiques en fonction du type d’erreur. Si l’utilisateur ne parvient toujours pas à se connecter, recueillez des informations supplémentaires, puis recherchez une aide supplémentaire.

## <a name="what-do-you-want-to-do"></a>Que souhaitez-vous faire ?
<a name="top"> </a>

> [Rechercher les causes courantes des erreurs de connexion à Skype Entreprise Online](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [Suivre la procédure de résolution d’une erreur spécifique (Entreprise uniquement)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [Ajouter une entrée de pare-feu pour msoidsvc.exe à votre serveur proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [Mettre à jour les paramètres DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [Installer un certificat SSL tiers sur votre serveur ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [Mettre à jour les informations d’identification de sécurité](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [Modifier les clés de Registre TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [Mettre à jour les paramètres utilisateur dans Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [Utiliser le guide de résolution des problèmes du Support Microsoft](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [Recueillir d’autres informations et rechercher de l’aide supplémentaire](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Rechercher les causes courantes des erreurs de connexion à Skype Entreprise Online
<a name="toc323194094"> </a>

La plupart des problèmes de connexion peuvent être ramenés à un petit nombre de causes, sont bon nombre sont faciles à corriger. Le tableau ci-dessous répertorie certaines des causes courantes des erreurs de connexion, ainsi que les étapes que vous ou les utilisateurs pouvez suivre pour les résoudre.


| **Cause possible**                                                                                                                                                    | **Solution**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Durant la connexion, une boîte de dialogue affiche le message suivant : **ne peut pas vérifier que le serveur est fiable pour que vous puissiez vous connecter. Voulez-vous vous connecter ?** <br/> | Vérifiez que le nom de domaine mentionné dans la boîte de dialogue correspond à un serveur approuvé au sein de votre organisation? Par exemple, **domainname.contoso.com**. Demandez à l’utilisateur d’activer la case à cocher **Toujours faire confiance à ce serveur**, puis cliquez sur **Se connecter**. <br/> Les clients Entreprise peuvent éviter que ce message s’affiche quand un utilisateur se connecte pour la première fois en modifiant le Registre Windows sur l’ordinateur de chaque utilisateur. Pour plus de détails, voir [Modifier les clés de Registre TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
| Adresse de connexion, nom d’utilisateur ou mot de passe incorrects  <br/>                                                                                                               | Vérifiez que le nom et le mot de passe de connexion de l’utilisateur sont corrects. <br/>  Vérifiez que le nom d’utilisateur est au format suivant : <strong>bobk@contoso.com</strong>. Ce format peut différer de celui utilisé lors de la connexion au réseau de votre organisation.  <br/>  Demandez à l’utilisateur de réessayer de se connecter. <br/>                                                                                                                                                                                                                             |
| Mot de passe oublié  <br/>                                                                                                                                             | Réinitialisez le mot de passe de l’utilisateur et communiquez-lui son nouveau mot de passe temporaire.  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Absence de licence pour utiliser Skype Entreprise Online  <br/>                                                                                                                  | Vérifiez que l’utilisateur est inscrit en tant qu’utilisateur de Skype Entreprise Online. S’il ne l’est pas, inscrivez-le et demandez-lui de se reconnecter.  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| Version incorrecte de Skype Entreprise Online installée  <br/>                                                                                                           | En règle générale, ce problème est associé à un message d’erreur contenant la phrase suivante : **le service d’authentification n’est pas compatible avec cette version du programme**.  <br/> Demandez à l’utilisateur de désinstaller, puis de réinstaller Skype Entreprise Online à partir du Centre d’administration Microsoft 365.  <br/>                                                                                                                                                                                                                                                    |
| Problème d’acquisition d’un certificat personnel requis pour se connecter  <br/>                                                                                           | Si l’adresse de connexion de l’utilisateur a changé récemment, il se peut que vous deviez supprimer les données de connexion mises en cache. Demandez à l’utilisateur de se déconnecter, cliquez sur le lien Supprimer mes informations de connexion dans l’écran de connexion, puis réessayez.  <br/>                                                                                                                                                                                                                                                                                                                                |
| Vous avez créé un nom de domaine personnalisé et les modifications n’ont peut-être pas fini de se propager dans le système.  <br/>                                                         | Commencez par vérifier que vous avez modifié les enregistrements Domain Name Service (DNS) pour refléter la modification.  <br/> Si vous avez déjà modifié les DNS correctement, invitez l’utilisateur à essayer de se connecter plus tard. L’application des modifications de DNS sur l’ensemble du système peut prendre jusqu’à 72 heures pour se refléter sur l’ensemble du système.  <br/>                                                                                                                                                                                                                                                        |
| L’horloge système n’est pas synchronisée avec celle du serveur  <br/>                                                                                                                     | Assurez-vous que votre contrôleur de domaine réseau se synchronise avec une source de temps externe fiable. Si vous souhaitez en savoir plus sur ce sujet, veuillez consulter l’article 816042 de la Base de connaissances Microsoft [Configuration d’un serveur de temps de référence dans Windows Server](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/>                                                                                                                                                                                                                                          |

Pour résoudre les erreurs de connexion à Skype Entreprise Online, commencez par éliminer les principales causes des problèmes de connexion. Si nécessaire, vous pouvez suivre des étapes de résolution spécifiques en fonction du type d’erreur. Si l’utilisateur ne parvient toujours pas à se connecter, recueillez des informations supplémentaires, puis recherchez une aide supplémentaire.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Suivre la procédure de résolution d’une erreur spécifique (Entreprise uniquement)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Ces instructions sont destinées principalement aux clients disposant d’un compte Microsoft Office 365 Plan E. Si vous êtes un client Office 365 Plan P, veuillez passer à la section suivante, [Recueillir d’autres informations et rechercher de l’aide supplémentaire](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).

Si l’utilisateur ne peut pas se connecter après avoir essayé les suggestions de la section précédente, vous pouvez procéder à une résolution des problèmes plus précise, axée sur le type d’erreur rencontré. Le tableau ci-dessous répertorie les principaux messages d’erreur et leurs causes probables. Le tableau suivant décrit les procédures détaillées à suivre pour résoudre chaque problème.

|**Message d’erreur**|**Cause possible**|**Solution**|
|:-----|:-----|:-----|
|Adresse de connexion introuvable  <br/> |Les demandes de connexion provenant de l’Assistant de connexion Microsoft Online Services (msoidsvc.exe) ne passent pas à travers le pare-feu externe ou le serveur proxy.  <br/> |[Ajouter une entrée de pare-feu pour msoidsvc.exe au serveur proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Serveur temporairement indisponible  <br/> |Si votre organisation possède un domaine personnalisé, les paramètres DNS (Domain Name System) nécessaires sont peut-être manquants ou incorrects.  <br/> |[Mettre à jour les paramètres DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Serveur temporairement indisponible  <br/> |Si votre organisation utilise l’authentification unique avec les services ADFS (services de fédération Active Directory ), il est possible que vous ayez eu recours à un certificat SSL (Secure Socket Layer) auto-signé au lieu d’un certificat provenant d’une autorité de certification tierce.  <br/> |[Installer un certificat SSL tiers sur votre serveur ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problème d’acquisition d’un certificat personnel requis pour se connecter  <br/> |Si vous avez déjà supprimé les données de serveur mises en cache utilisées pour la connexion et que l’erreur persiste, il se peut que les informations d’authentification de l’utilisateur soient endommagées ou qu’un dossier RSA sur l’ordinateur de l’utilisateur bloque l’authentification.  <br/> |[Mettre à jour les informations d’identification de sécurité](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Boîte de dialogue relative à l’approbation du certificat s’affichant lorsque l’utilisateur se connecte pour la première fois.  <br/> |La boîte de dialogue apparaît si votre serveur Skype Entreprise n’est pas encore répertorié dans la clé de Registre **TrustModelData**. <br/> |[Modifier les clés de Registre TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|L’utilisateur ne prend pas en charge le protocole SIP  <br/> |Si votre organisation utilise une version plus ancienne de Microsoft Office Communications Server ou de Microsoft Lync Server 2010, il est possible que vos utilisateurs n’aient pas été supprimés du serveur avant sa désaffectation. Par conséquent, l’attribut **msRTCSIP-UserEnabled** est encore défini sur **FALSE** dans Active Directory Domain Services. <br/> |[Mettre à jour les paramètres utilisateur dans Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Ajouter une entrée de pare-feu pour msoidsvc.exe à votre serveur proxy
<a name="add-a-firewall"> </a>

Cette procédure peut résoudre l’erreur suivante : **Adresse de connexion introuvable**.

> [!NOTE]
> Pour la suite de cette procédure, nous partons du principe que vous utilisez Microsoft Forefront Threat Management Gateway (TMG) 2010. Si vous utilisez une autre solution de passerelle web, veuillez appliquer les paramètres décrits lors de l’étape 4, ci-dessous.


Pour créer une entrée d’application pour Msoidsvc.exe dans Forefront TMG 2010, procédez comme suit :

1. Dans le volet gauche de Forefront, cliquez sur **Réseau**.

2. Cliquez sur l’onglet **Réseau**. Sous l’onglet **Tâches** du volet droit, cliquez sur **Configurer les paramètres du client Forefront TMG**.

3. Dans la boîte de dialogue **Paramètres du client Forefront TMG**, cliquez sur **Nouveau**.

4. Dans la boîte de dialogue **Paramètre d’entrée de l’application**, configurez les règles suivantes :

|**Application**|**Clé**|**Valeur**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

Pour plus d’informations, voir l’article 2409256 de la Base de connaissances Microsoft intitulé : [Vous ne pouvez pas vous connecter à Skype Entreprise Online parce qu’un pare-feu local bloque la connexion](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).

### <a name="update-dns-settings"></a>Mettre à jour les paramètres DNS
<a name="update-dns-service"> </a>

Si votre organisation possède un domaine personnalisé, cette procédure peut résoudre l’erreur suivante : **Serveur temporairement indisponible**.

- Contactez le bureau d’enregistrement de noms de domaine pour obtenir des informations sur l’ajout de l’enregistrement CNAME suivant à votre domaine :

  - **Type d’enregistrement DNS** : CNAME

  - **Nom** : sip

  - **Valeur/destination** : sipdir.online.Lync.com

Pour plus d’informations, voir l’article 2566790 de la Base de connaissances Microsoft intitulé : [Résolution des problèmes de configuration DNS de Skype Entreprise Online dans Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Installer un certificat SSL tiers sur votre serveur ADFS
<a name="verify-upn-and"> </a>

Pour installer un certificat SSL tiers sur le serveur ADFS (Active Domain Federation Services), procédez comme suit :

1. Obtenez un certificat SSL auprès d’une autorité de certification tierce telle que VeriSign ou Thawte.

2. Installez le certificat sur votre serveur ADFS à l’aide de la console de gestion ADFS.

### <a name="update-security-credentials"></a>Mettre à jour les informations d’identification de sécurité
<a name="update-security-credentials"> </a>

Cette procédure peut permettre de résoudre l’erreur suivante : **Un problème s’est produit lors de l’acquisition d’un certificat personnel nécessaire pour établir la connexion**.

Pour éliminer les éventuels problèmes d’informations d’identification ou de certificats, commencez par renouveler le certificat de l’utilisateur dans le Gestionnaire de certificats Windows. Pour cela, merci de procéder comme suit :

1. Ouvrez le Gestionnaire de certificats Windows. Pour ce faire, cliquez sur **Démarrer**, puis **Exécuter**, tapez **certmgr.msc**, puis cliquez sur **OK**.

2. Double-cliquez sur **Personnel**, puis sur **Certificats**.

3. Effectuez un tri sur la colonne **Délivré par**, puis recherchez un certificat émis par Serveur de communications.

4. Cliquez avec le bouton droit sur le certificat, puis cliquez sur **Supprimer**.

Ensuite, si l’utilisateur exécute Windows 7, supprimez ses informations d’identification stockées dans le Gestionnaire d’informations d’identification Windows. Pour cela, merci de procéder comme suit :

1. Cliquez sur **Démarrer**, sur **Panneau de configuration**, puis sur **Gestionnaire d’informations d’identification**.

2. Recherchez le jeu informations d’identification utilisées pour la connexion à Skype Entreprise Online.

3. Développez le jeu d’informations d’identification, puis cliquez sur **Supprimer de l’archivage sécurisé**.

4. Reconnectez-vous et réentrez les informations d’identification de l’utilisateur.

Enfin, si l’utilisateur ne parvient toujours pas à se connecter après la mise à jour de ses informations d’identification, essayez de supprimer le dossier RSA de l’ordinateur de l’utilisateur, car celui-ci peut empêcher l’accomplissement du processus d’authentification de l’utilisateur :

1. Connectez-vous à l’ordinateur de l’utilisateur à l’aide d’un compte d’administrateur.

2. Si nécessaire, activez l’option d’affichage de dossier **Afficher les fichiers masqués**.

3. Tapez les informations suivantes dans la barre d’adresses de l’Explorateur de fichiers : **C:\\Documents and Settings\\NomUtilisateur\\Application Data\\Microsoft\\Crypto\\RSA**, où **_NomUtilisateur_** est le nom de votre connexion à Windows.

4. Supprimez tout dossier dont le nom commence par **S-1-5-21-**, suivi d’une chaîne de chiffres.

### <a name="modify-trustmodeldata-registry-keys"></a>Modifier les clés de Registre TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Lorsqu’un utilisateur se connecte pour la première fois, il se peut qu’une boîte de dialogue, semblable à la suivante, s’affiche : **Impossible de vérifier que le serveur est approuvé comme adresse de connexion. Voulez-vous vous connecter ?** Il s’agit d’une fonctionnalité de sécurité, et non d’une erreur. Toutefois, vous pouvez empêcher l’affichage de cette boîte de dialogue à l’aide d’un objet de stratégie de groupe (GPO) pour mettre à jour les ordinateurs des utilisateurs avec votre nom de domaine avant leur première connexion. Pour ce faire, procédez comme suit :

- Créez et déployez un objet de stratégie de groupe qui ajoute votre nom de domaine Skype Entreprise (par exemple, NomDomaine.contoso.com) à la valeur actuelle de HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.

> [!IMPORTANT]
>  Vous devez *ajouter* votre nom de domaine à la valeur existante, pas simplement la remplacer.

Pour plus d’informations, voir l’article 2531068 de la Base de connaissances Microsoft intitulé [Skype Entreprise (Lync) ne peut pas vérifier que le serveur est fiable pour votre adresse de connexion](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).

### <a name="update-user-settings-in-active-directory"></a>Mettre à jour les paramètres utilisateur dans Active Directory
<a name="update-user-settings"> </a>

Si votre organisation utilise une version plus ancienne de Microsoft Office Communications Server ou de Microsoft Lync Server 2010, il est possible que vos utilisateurs n’aient pas été supprimés du serveur avant sa désaffectation. Par conséquent, l’attribut **msRTCSIP-UserEnabled** est encore défini sur **FALSE** dans Active Directory Domain Services.

Pour résoudre ce problème, procédez comme suit :

1. Mettez à jour l’attribut **msRTCSIP-UserEnabled** pour tous les utilisateurs affectés sur **TRUE**.

2. Réexécutez Microsoft Online Services - Outil de synchronisation d'annuaires (DirSync). Pour plus de détails, voir [Intégrer vos annuaires locaux avec Azure Active Directory](/azure/active-directory/hybrid/whatis-hybrid-identity).

Pour résoudre les erreurs de connexion à Skype Entreprise Online, commencez par éliminer les causes les plus courantes des problèmes de connexion. Si nécessaire, vous pouvez suivre des étapes de résolution spécifiques en fonction du type d’erreur. Si l’utilisateur ne parvient toujours pas à se connecter, recueillez des informations supplémentaires, puis recherchez une aide supplémentaire.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Utiliser le guide de résolution des problèmes du Support Microsoft
<a name="toc325626447"> </a>

Si vous n’êtes toujours pas en mesure de résoudre les problèmes de connexion de l’utilisateur, consultez les suggestions présentées dans l’article 2541980 de la Base de connaissances Microsoft intitulé [Comment résoudre les problèmes de connexion dans Skype Entreprise Online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).

## <a name="collect-more-information-and-seek-additional-help"></a>Recueillir d’autres informations et rechercher de l’aide supplémentaire
<a name="collect-more-information"> </a>

Si vous avez suivi les conseils ci-dessus et ne parvenez toujours pas à résoudre les problèmes de connexion, veuillez recueillir des informations supplémentaires, puis contacter le support technique. Pour cela, merci de procéder comme suit :

1. Récupérez les fichiers journaux et les détails du Journal des événements Windows depuis l’ordinateur de l’utilisateur. Si vous désirez consulter des instructions détaillées, veuillez vous reporter à la rubrique d’aide utilisateur [Activation de la journalisation des erreurs dans Skype Entreprise (Lync)](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).

2. Veuillez transmettre les fichiers journaux et les informations détaillées sur l’erreur au support technique de Microsoft.

Vous serez peut-être invité à fournir des informations de diagnostic supplémentaires en installant le Kit de ressources de support Microsoft Online Services Diagnostic and Logging (MOSDAL) sur l’ordinateur de l’utilisateur concerné par le problème. Si vous désirez en savoir plus sur ce sujet, veuillez consulter l’article [Utilisation du Kit de ressources de support MOSDAL](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).

Pour résoudre les erreurs de connexion à Skype Entreprise Online, commencez par éliminer les principales causes des problèmes de connexion. Si nécessaire, vous pouvez suivre des étapes de résolution spécifiques en fonction du type d’erreur. Si l’utilisateur ne parvient toujours pas à se connecter, recueillez des informations supplémentaires, puis recherchez une aide supplémentaire.

## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)