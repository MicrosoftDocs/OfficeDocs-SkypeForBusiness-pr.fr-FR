---
title: Gérer les applications approuvées
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Une application approuvée est une application basée sur le Kit de développement logiciel (SDK) UCMA (Microsoft Unified Communications Managed API) 3.0 Core approuvé par Skype Entreprise Server.
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674536"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gérer les applications approuvées dans Skype Entreprise Server

Une *application approuvée* est une application basée sur le Kit de développement logiciel (SDK) UCMA (Microsoft Unified Communications Managed API) 3.0 Core approuvé par Skype Entreprise Server. Pour plus d’informations sur les applications UCMA, consultez la documentation du Kit de développement logiciel (SDK) Core de l’API managée des communications unifiées 3.0 à l’adresse https://go.microsoft.com/fwlink/p/?linkId=210320.

Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. 

Cet article explique comment configurer un nouveau serveur d’applications approuvé, afficher la liste des applications approuvées et afficher les informations d’application approuvées. 

## <a name="configure-a-new-trusted-application-server"></a>Configurer un nouveau serveur d’applications approuvé

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrer le Générateur de topologie : cliquez sur **Démarrer**, cliquez sur **Tous les programmes**, cliquez sur **Skype Entreprise Server**, puis sur **Skype Entreprise Server Générateur de topologie**.

3.  Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue **Enregistrer la topologie sous** , cliquez sur le fichier Générateur de topologie que vous souhaitez utiliser, puis cliquez sur **Enregistrer**.

5.  Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications approuvés**, puis cliquez sur **Nouveau pool d’applications approuvées**.

6.  Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.

7.  Dans la page **Sélectionner le tronçon suivant**, dans la liste, sélectionnez le Skype Entreprise Server pool frontal.

8.  Cliquez sur **Terminer**.

9.  Sélectionnez le nœud supérieur **Skype Entreprise Server**, puis, dans le menu **Actions**, cliquez sur **Publier la topologie**.
    
    Le **pool d’applications** approuvées doit avoir été créé avec succès et associé au pool frontal approprié.


## <a name="view-a-list-of-trusted-applications"></a>Afficher la liste des applications approuvées

Vous pouvez utiliser la Skype Entreprise Server Panneau de configuration pour afficher la liste des applications approuvées que vous avez déployées dans votre environnement Skype Entreprise Server. Une application approuvée est une application basée sur le Kit de développement logiciel (SDK) UCMA (Microsoft Unified Communications Managed API) 3.0 Core approuvé par Skype Entreprise Server. Cette relation d’approbation est résumée dans la liste suivante :

  - Les applications approuvées ne sont pas mises à l’épreuve pour l’authentification par Skype Entreprise Server.

  - Les applications approuvées ne sont pas limitées par Skype Entreprise Server pour les transactions SIP, les connexions ou les appels VoIP (Voice over Internet Protocol) sortants.

  - Les applications approuvées peuvent emprunter l’identité de n’importe quel utilisateur et peuvent participer à des conférences sans apparaître dans les listes.

  - Les applications approuvées sont hautement disponibles et résilientes.

Dans le Skype Entreprise Server Panneau de configuration, vous pouvez voir le nom des applications, le pool où elles s’exécutent et le port qu’elles utilisent.


### <a name="to-view-a-list-of-trusted-applications"></a>Pour afficher une liste d’applications approuvées

1.  Avec un compte d’utilisateur affecté au rôle CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype Entreprise Server, consultez [le contrôle d’accès en fonction du rôle (RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration.

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **Application approuvée**.

4.  Dans la page **Application** approuvée, cliquez sur un en-tête de colonne pour trier les applications, si nécessaire.


## <a name="view-trusted-application-information"></a>Afficher les informations d’application approuvée

Vous pouvez afficher des informations sur vos applications approuvées à l’aide de Windows PowerShell et de l’applet **de commande Get-CsTrustedApplication**. Cette applet de commande peut être exécutée à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Pour afficher les applications approuvées

Pour afficher toutes vos applications approuvées, tapez la commande suivante dans le Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
   **Get-CsConferenceDisclaimer**
    
   Cette commande retourne des informations identiques aux suivantes pour chaque application approuvée :
    
   Identité : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool : 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   Displayname:<br/>
   DisplayNumber :<br/>
   LineURI :<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages : {}<br/>
   EnterpriseVoiceEnabled : True<br/>
   ExUmEnabled : False<br/>
   Activé : True<br/>
    
   Pour plus d’informations, voir [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).