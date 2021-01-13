---
title: Activation ou désactivation de l’accès utilisateur distant
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent via Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes à l’aide de Skype Entreprise Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817394"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Activer ou désactiver l’accès des utilisateurs distants dans Skype Entreprise Server

Les utilisateurs distants sont des utilisateurs de votre organisation qui ont une identité Active Directory persistante au sein de l’organisation. Les utilisateurs distants se connectent souvent à Skype Entreprise Server depuis l’extérieur de votre réseau à l’aide d’un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre organisation. Les utilisateurs distants incluent les employés travaillant à domicile ou sur la route, ainsi que d’autres travailleurs à distance, tels que des fournisseurs de confiance, qui ont reçu des informations d’identification d’entreprise. Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent via Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes à l’aide de Skype Entreprise Server.

Pour prendre en charge l’accès des utilisateurs distants, vous devez l’activer (pour l’ensemble de votre entreprise). Si vous souhaitez plus tard empêcher temporairement ou définitivement l’accès des utilisateurs distants, vous pouvez le désactiver pour votre entreprise. Suivez la procédure dans cette section pour activer ou désactiver l’accès des utilisateurs distants pour votre entreprise.


> [!NOTE]  
> L’activation de l’accès des utilisateurs distants spécifie uniquement que vos serveurs exécutant le service Edge d’accès gèrent les communications avec des utilisateurs distants, mais que les utilisateurs distants ne peuvent pas participer à des conférences ou des messages instantanés dans votre organisation tant que vous n’avez pas configuré au moins une stratégie pour gérer l’utilisation de l’accès des utilisateurs distants. Les paramètres de stratégie Skype Entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet. Pour plus d’informations sur la configuration des stratégies pour l’utilisation de l’accès des utilisateurs distants, voir Configurer des stratégies pour contrôler l’accès des utilisateurs distants [dans Skype Entreprise Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs distants pour votre entreprise

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.

4.  Sur la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs distants pour votre entreprise, activez la case à cocher **Activer l’accès des utilisateurs distants**.
    
      - Pour désactiver l’accès des utilisateurs distants pour votre entreprise, désactivez la case à cocher **Activer l’accès des utilisateurs distants**.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs distants de se connectent à vos serveurs exécutant Skype Entreprise Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants. Pour plus d’informations, voir Configurer des stratégies pour contrôler l’accès des utilisateurs [distants dans Skype Entreprise Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès des utilisateurs distants à l’Windows PowerShell cmdlets

L’accès des utilisateurs distants peut être géré à l’Windows PowerShell l'Set-CsAccessEdgeConfiguration cmdlet. Cette cmdlet peut être exécuté à partir de Skype Entreprise Server 2013 Management Shell ou d’une session distante de Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Pour activer l’accès des utilisateurs distants

  - Pour activer l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Pour désactiver l’accès des utilisateurs distants

  - Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


