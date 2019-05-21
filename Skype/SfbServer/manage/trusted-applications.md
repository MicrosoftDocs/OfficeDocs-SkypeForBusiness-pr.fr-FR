---
title: Gérer les applications approuvées
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une application fiable est une application basée sur le kit de développement logiciel (Unified Communications Managed API UCMA) 3,0 principal du SDK approuvé par Skype entreprise Server.
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275065"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gestion des applications approuvées dans Skype entreprise Server

Une *application fiable* est une application basée sur le kit de développement logiciel (Unified Communications Managed API UCMA) 3,0 principal du SDK approuvé par Skype entreprise Server. Pour plus d’informations sur les applications UCMA, voir la documentation relative au kit de développement logiciel http://go.microsoft.com/fwlink/p/?linkId=210320unifié API 3,0 principal du SDK.

Pour la publication, l’activation ou la désactivation d’une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. 

Cet article vous explique comment configurer un nouveau serveur d’applications de confiance, afficher une liste des applications approuvées et afficher des informations sur les applications approuvées. 

## <a name="configure-a-new-trusted-application-server"></a>Configurer un nouveau serveur d’applications de confiance

1.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Générateur de topologie Skype entreprise Server**.

3.  Sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue **enregistrer la topologie comme** , cliquez sur le fichier de générateur de topologie que vous voulez utiliser, puis cliquez sur **Enregistrer**.

5.  Dans le volet gauche, cliquez avec le bouton droit sur **serveurs d’applications de confiance**, puis cliquez sur **nouveau pool d’applications approuvés**.

6.  Entrez le **nom de domaine complet (FQDN** ) du pool d’applications de confiance, puis choisissez s’il s’agit d’un serveur unique ou d’un serveur, puis cliquez sur **suivant**.

7.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez la liste frontale Skype entreprise Server.

8.  Cliquez sur **Terminer**.

9.  Sélectionnez le nœud principal **Skype entreprise Server**, puis, dans le menu **actions** , cliquez sur **publier la topologie**.
    
    Le **pool d’applications approuvé** doit avoir été créé avec succès et associé au pool frontal approprié.


## <a name="view-a-list-of-trusted-applications"></a>Afficher une liste des applications approuvées

Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour afficher une liste des applications approuvées que vous avez déployées dans votre environnement Skype entreprise Server. Une application fiable est une application basée sur le kit de développement logiciel (Unified Communications Managed API UCMA) 3,0 principal du SDK approuvé par Skype entreprise Server. Cette relation d’approbation est résumée dans la liste suivante:

  - Les applications approuvées ne sont pas confrontées à l’authentification par Skype entreprise Server.

  - Les applications approuvées ne sont pas limitées par Skype entreprise Server pour les transactions SIP, les connexions ou les appels voix sur IP sortants.

  - Les applications approuvées peuvent emprunter l’identité d’un utilisateur et participer à des conférences sans apparaître dans les listes.

  - Les applications approuvées sont hautement disponibles et résilientes.

Dans le panneau de configuration Skype entreprise Server, vous pouvez voir le nom de l’application, le pool sur lequel elle s’exécute et le port utilisé.


### <a name="to-view-a-list-of-trusted-applications"></a>Pour afficher une liste des applications approuvées

1.  À partir d’un compte d’utilisateur affecté au CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype entreprise Server, voir [contrôle d’accès basé sur les rôles (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Topology**, puis sur **application sécurisée**.

4.  Dans la page **application fiable** , cliquez sur un en-tête de colonne pour trier les applications si nécessaire.


## <a name="view-trusted-application-information"></a>Afficher les informations sur l’application fiable

Vous pouvez afficher des informations sur vos applications approuvées à l’aide de Windows PowerShell et de l’applet **de passe Get-CsTrustedApplication** . Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Pour afficher des applications approuvées

Pour afficher toutes vos applications approuvées, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:
    
        Get-CsConferenceDisclaimer
    
   Cette commande renvoie des informations similaires à ce qui suit pour chaque application fiable:
    
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
    
   Pour plus d’informations, consultez la rubrique [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
