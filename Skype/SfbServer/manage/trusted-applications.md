---
title: Gérer les applications approuvées
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une application approuvée est une application basée sur le Kit de développement Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype pour Business Server.
ms.openlocfilehash: 3ca8621148a4b6ce3530f23a61312f63f3d3cd30
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882141"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gérer les applications approuvées dans Skype pour Business Server

Une *application approuvée* est une application basée sur le Kit de développement Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype pour Business Server. Pour plus d’informations sur les applications UCMA, consultez la rubrique « Unified Communications gérées API 3.0 Core Documentation du kit SDK » http://go.microsoft.com/fwlink/p/?linkId=210320.

Pour publier avec succès, activer ou désactiver une topologie lors de l’ajout ou suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et administrateurs du domaine. 

Utilisez cet article pour apprendre à configurer un nouveau serveur d’applications approuvées, afficher la liste des applications approuvées et d’afficher des informations d’application approuvée. 

## <a name="configure-a-new-trusted-application-server"></a>Configurer un nouveau serveur d’applications approuvées

1.  Ouvrez une session l’ordinateur où le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour le Générateur de topologie Business Server**.

3.  Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue **Enregistrer la topologie sous** , cliquez sur le fichier du Générateur de topologie que vous souhaitez utiliser, puis cliquez sur **Enregistrer**.

5.  Dans le volet gauche, cliquez sur **serveurs d’applications approuvées**, puis cliquez sur **Nouveau Pool d’applications approuvées**.

6.  Entrez le **Nom complet du Pool** du pool d’applications approuvées, sélectionnez s’il sera un serveur unique ou plusieurs serveurs et puis cliquez sur **suivant**.

7.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le Skype pour Business Server un pool frontal.

8.  Cliquez sur **Terminer**.

9.  Sélectionnez le nœud supérieur **Skype pour Business Server**, puis, dans le menu **Actions** , cliquez sur **Publier la topologie**.
    
    Le **Pool d’applications approuvées** doivent créé avec succès et associé au pool frontal correct.


## <a name="view-a-list-of-trusted-applications"></a>Afficher la liste des applications approuvées

Vous pouvez utiliser la Skype pour Business Server Control Panel pour afficher la liste des applications approuvées que vous avez déployé dans votre Skype pour un environnement Business Server. Une application approuvée est une application basée sur le Kit de développement Microsoft Unified Communications Managed API (UCMA) 3.0 Core approuvé par Skype pour Business Server. Cette relation d’approbation est résumée dans la liste suivante :

  - Les applications approuvées ne requiert pas l’authentification par Skype Business Server.

  - Les applications approuvées ne sont pas limitées par Skype pour Business Server pour les transactions SIP, les connexions ou sortant voix sur IP (VoIP) appels.

  - Les applications approuvées peuvent emprunter l’identité d’un utilisateur et participer à des conférences sans apparaître dans les listes.

  - Les applications approuvées sont hautement disponibles et résistantes.

Dans Skype pour le panneau de configuration serveur Business, vous pouvez voir le nom des applications, le pool dans lequel elles s’exécutent et le port qu’elles utilisent.


### <a name="to-view-a-list-of-trusted-applications"></a>Pour afficher la liste des applications approuvées

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsServerAdministrator, CsAdministrator, est CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype pour Business Server, voir [contrôle d’accès basé sur un rôle (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.

3.  Dans la barre de navigation de gauche, cliquez sur **la topologie**, puis cliquez sur **Application approuvée**.

4.  Dans la page **Application approuvée** , cliquez sur un en-tête de colonne pour trier les applications, si nécessaire.


## <a name="view-trusted-application-information"></a>Afficher les informations d’application approuvée

Vous pouvez afficher des informations sur les applications approuvées à l’aide de Windows PowerShell et l’applet de commande **Get-CsTrustedApplication** . Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Pour afficher les applications approuvées

Pour afficher toutes les applications approuvées, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
        Get-CsConferenceDisclaimer
    
   Cette commande retourne des informations semblables à ce qui suit pour chaque application approuvée :
    
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
