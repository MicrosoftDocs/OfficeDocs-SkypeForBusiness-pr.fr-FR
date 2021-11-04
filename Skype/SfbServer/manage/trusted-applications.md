---
title: Gérer les applications fiables
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Une application fiable est une application basée sur microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK qui est approuvé par Skype Entreprise Server.
ms.openlocfilehash: 4164f00b787ac8f234d13ba7c31e54c79cb1efd7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750163"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gérer les applications fiables dans Skype Entreprise Server

Une *application fiable* est une application basée sur microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK qui est approuvé par les Skype Entreprise Server. Pour plus d’informations sur les applications UCMA, voir « Documentation du SDK Unified Communications Managed API 3.0 Core » sur https://go.microsoft.com/fwlink/p/?linkId=210320 .

Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. 

Utilisez cet article pour découvrir comment configurer un nouveau serveur d’applications approuvé, afficher une liste d’applications fiables et afficher des informations sur les applications de confiance. 

## <a name="configure-a-new-trusted-application-server"></a>Configurer un nouveau serveur d’applications fiables

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le Générateur de topologies : **cliquez** sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server,** puis sur Skype Entreprise Server **générateur de topologies.**

3.  Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue Enregistrer la topologie **sous,** cliquez sur le fichier du Générateur de topologie que vous souhaitez utiliser, puis cliquez sur **Enregistrer.**

5.  Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications** de confiance, puis cliquez sur **Nouveau pool d’applications fiables.**

6.  Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.

7.  Dans la page **Sélectionner le saut suivant,** dans la liste, sélectionnez Skype Entreprise Server pool frontal.

8.  Cliquez sur **Terminer**.

9.  Sélectionnez le nœud supérieur **Skype Entreprise Server,** puis, dans le menu **Actions,** cliquez sur **Publier la topologie.**
    
    Le **pool d’applications** fiables doit avoir été créé avec succès et associé au pool frontal correct.


## <a name="view-a-list-of-trusted-applications"></a>Afficher une liste d’applications fiables

Vous pouvez utiliser le Panneau de Skype Entreprise Server pour afficher la liste des applications de confiance que vous avez déployées dans votre environnement Skype Entreprise Server web. Une application fiable est une application basée sur microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK qui est approuvé par Skype Entreprise Server. Cette relation d’confiance est résumée dans la liste suivante :

  - L’authentification des applications fiables n’est pas Skype Entreprise Server.

  - Les applications fiables ne sont pas limitées par Skype Entreprise Server pour les transactions SIP, les connexions ou les appels VoIP (Voice over Internet Protocol) sortants.

  - Les applications fiables peuvent usurper l’identité de n’importe quel utilisateur et participer à des conférences sans apparaître dans les listes.

  - Les applications fiables sont hautement disponibles et résilientes.

Dans le Skype Entreprise Server de contrôle, vous pouvez voir le nom des applications, le pool dans lequel elles s’exécutent et le port qu’elles utilisent.


### <a name="to-view-a-list-of-trusted-applications"></a>Pour afficher une liste d’applications fiables

1.  Avec un compte d’utilisateur affecté au rôle CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfin Skype Entreprise Server, voir Contrôle d’accès basé sur un rôle [(RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie,** puis sur **Application de confiance.**

4.  Dans la page **Application de** confiance, cliquez sur un en-tête de colonne pour trier les applications, si nécessaire.


## <a name="view-trusted-application-information"></a>Afficher les informations sur les applications fiables

Vous pouvez afficher des informations sur vos applications de confiance à l’aide Windows PowerShell et de l’cmdlet **Get-CsTrustedApplication.** Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Pour afficher les applications approuvées

Pour afficher toutes vos applications de confiance, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
   **Get-CsConferenceDisclaimer**
    
   Cette commande retourne des informations identiques aux suivantes pour chaque application approuvée :
    
   Identity : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool : 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   DisplayName :<br/>
   DisplayNumber :<br/>
   LineURI :<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages : {}<br/>
   EnterpriseVoiceEnabled : True<br/>
   ExUmEnabled : False<br/>
   Activé : True<br/>
    
   Pour plus d’informations, voir [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).