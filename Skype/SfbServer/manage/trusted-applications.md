---
title: Gérer les applications approuvées
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une application approuvée est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Skype entreprise Server.
ms.openlocfilehash: c5c1a62440ebb98974cee5771c13cf0e5acc55c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151224"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gérer les applications approuvées dans Skype entreprise Server

Une *application approuvée* est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Skype entreprise Server. Pour plus d’informations sur les applications UCMA, voir «documentation du https://go.microsoft.com/fwlink/p/?linkId=210320Kit de développement logiciel (SDK) Unified Communications Managed API 3,0.

Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. 

Cet article explique comment configurer un nouveau serveur d’applications approuvées, afficher la liste des applications approuvées et afficher les informations sur les applications approuvées. 

## <a name="configure-a-new-trusted-application-server"></a>Configurer un nouveau serveur d’applications approuvées

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Générateur de topologie Skype entreprise Server**.

3.  Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue **enregistrer la topologie sous** , cliquez sur le fichier du générateur de topologies que vous souhaitez utiliser, puis cliquez sur **Enregistrer**.

5.  Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications approuvées**, puis cliquez sur **nouveau pool d’applications approuvées**.

6.  Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.

7.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Skype entreprise Server.

8.  Cliquez sur**Terminer**.

9.  Sélectionnez le nœud supérieur **Skype entreprise Server**, puis, dans le menu **actions** , cliquez sur **publier la topologie**.
    
    Le **pool d’applications approuvées** doit avoir été créé avec succès et associé au pool frontal correct.


## <a name="view-a-list-of-trusted-applications"></a>Afficher la liste des applications approuvées

Vous pouvez utiliser le panneau de configuration de Skype entreprise Server pour afficher la liste des applications approuvées que vous avez déployées dans votre environnement Skype entreprise Server. Une application approuvée est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Skype entreprise Server. Cette relation d’approbation est résumée dans la liste suivante :

  - Les applications approuvées ne sont pas contestées pour l’authentification par Skype entreprise Server.

  - Les applications approuvées ne sont pas limitées par Skype entreprise Server pour les transactions SIP, les connexions ou les appels VoIP (Voice over Internet Protocol) sortants.

  - Les applications approuvées peuvent emprunter l’identité de n’importe quel utilisateur et participer à des conférences sans apparaître dans les listes.

  - Les applications approuvées sont hautement disponibles et résilientes.

Dans le panneau de configuration de Skype entreprise Server, vous pouvez voir le nom des applications, le pool où elles s’exécutent, ainsi que le port qu’elles utilisent.


### <a name="to-view-a-list-of-trusted-applications"></a>Pour afficher la liste des applications approuvées

1.  Avec un compte d’utilisateur affecté au rôle CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype entreprise Server, consultez la rubrique [contrôle d’accès basé sur un rôle (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3.  Dans la barre de navigation de gauche, cliquez sur **topologie**, puis sur **application approuvée**.

4.  Sur la page **application approuvée** , cliquez sur un en-tête de colonne pour trier les applications, le cas échéant.


## <a name="view-trusted-application-information"></a>Afficher les informations de l’application approuvée

Vous pouvez afficher des informations sur vos applications approuvées à l’aide de Windows PowerShell et de la cmdlet **Get-CsTrustedApplication** . Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Pour afficher les applications approuvées

Pour afficher toutes vos applications approuvées, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :
    
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
