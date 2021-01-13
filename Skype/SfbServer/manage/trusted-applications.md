---
title: Gérer les applications fiables
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une application fiable est une application basée sur le SDK Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype Entreprise Server.
ms.openlocfilehash: e9d29371014d902bbee38e2f3871c5579634c0f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826274"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gérer les applications de confiance dans Skype Entreprise Server

Une *application fiable* est une application basée sur le SDK Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype Entreprise Server. Pour plus d’informations sur les applications UCMA, voir « Documentation du SDK Unified Communications Managed API 3.0 Core » sur https://go.microsoft.com/fwlink/p/?linkId=210320 .

Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. 

Utilisez cet article pour apprendre à configurer un nouveau serveur d’applications approuvé, afficher une liste d’applications fiables et afficher des informations sur les applications de confiance. 

## <a name="configure-a-new-trusted-application-server"></a>Configurer un nouveau serveur d’applications fiables

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le Générateur de topologie : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server,** puis sur Générateur de topologie **Skype Entreprise Server.**

3.  Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue Enregistrer la topologie **sous,** cliquez sur le fichier du Générateur de topologie que vous souhaitez utiliser, puis cliquez sur **Enregistrer.**

5.  Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications** de confiance, puis cliquez sur **Nouveau pool d’applications fiables.**

6.  Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.

7.  Dans la page **Sélectionner le saut suivant,** dans la liste, sélectionnez le pool frontal Skype Entreprise Server.

8.  Cliquez sur **Terminer**.

9.  Sélectionnez le nœud supérieur **Skype Entreprise Server,** puis, dans le menu **Actions,** cliquez sur **Publier la topologie.**
    
    Le **pool d’applications** fiables doit avoir été créé avec succès et associé au pool frontal correct.


## <a name="view-a-list-of-trusted-applications"></a>Afficher une liste d’applications fiables

Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour afficher la liste des applications de confiance que vous avez déployées dans votre environnement Skype Entreprise Server. Une application fiable est une application basée sur le SDK Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype Entreprise Server. Cette relation d’confiance est résumée dans la liste suivante :

  - L’authentification par Skype Entreprise Server ne demande pas d’authentification aux applications fiables.

  - Les applications fiables ne sont pas limitées par Skype Entreprise Server pour les transactions SIP, les connexions ou les appels VoIP (Voice over Internet Protocol) sortants.

  - Les applications fiables peuvent usurper l’identité de n’importe quel utilisateur et participer à des conférences sans apparaître dans les listes.

  - Les applications fiables sont hautement disponibles et résilientes.

Dans le Panneau de contrôle Skype Entreprise Server, vous pouvez voir le nom des applications, le pool dans lequel elles s’exécutent et le port qu’elles utilisent.


### <a name="to-view-a-list-of-trusted-applications"></a>Pour afficher une liste d’applications fiables

1.  Avec un compte d’utilisateur affecté au rôle CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfincis disponibles dans Skype Entreprise Server, voir Contrôle d’accès basé sur un rôle [(RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie,** puis sur **Application de confiance.**

4.  Dans la page **Application de** confiance, cliquez sur un en-tête de colonne pour trier les applications, si nécessaire.


## <a name="view-trusted-application-information"></a>Afficher les informations sur les applications fiables

Vous pouvez afficher des informations sur vos applications Windows PowerShell et l’cmdlet **Get-CsTrustedApplication.** Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Pour afficher les applications approuvées

Pour afficher toutes vos applications de confiance, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsConferenceDisclaimer
    
   Cette commande retourne des informations identiques aux suivantes pour chaque application approuvée :
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   Pour plus d’informations, voir [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
