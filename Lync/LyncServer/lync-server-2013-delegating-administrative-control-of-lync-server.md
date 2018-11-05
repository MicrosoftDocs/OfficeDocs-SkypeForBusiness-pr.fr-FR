---
title: 'Lync Server 2013 : Délégation du contrôle administratif de Lync Server'
TOCTitle: Délégation du contrôle administratif de Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520951(v=OCS.15)
ms:contentKeyID: 49296268
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Délégation du contrôle administratif de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Dans Lync Server 2013, les tâches d’administration sont déléguées aux utilisateurs via la nouvelle fonctionnalité de contrôle d’accès basé sur un rôle (RBAC). Lorsque vous installez Lync Server, plusieusr rôles RBAC sont créés automatiquement. Ces rôles correspondent aux groupes universels de sécurité dans services de domaine Active Directory. Par exemple, le rôle RBAC CsHelpDesk correspond au groupe CsHelpDesk disponible dans le conteneur Utilisateurs des services de domaine Active Directory. En outre, chaque rôle RBAC est affecté à plusieurs applets de commande Lync ServerWindows PowerShell. Ces applets de commande représentent les tâches que peuvent réaliser les utilisateurs auxquels le rôle RBAC concerné a été attribué. Par exemple, le rôle CsHelpDesk a été affecté aux applets de commande Lock-CsClientPin et UnlockCsClientPin. Cela implique que les utilisateurs auxquels le rôle CsHelpDesk a été attribué peuvent verrouiller et déverrouiller les codes confidentiels utilisateur. Cependant, l’applet de commande New-CsVoicePolicy n’a pas été affectée au rôle CsHelpDesk. Par conséquent, les utilisateurs auxquels le rôle CsHelpDesk a été attribué ne peuvent pas créer de nouvelles stratégies de voix.

## Consultation des informations sur les rôles RBAC

Vous pouvez récupérer les informations essentielles sur les rôles RBAC en exécutant la commande suivante directement depuis Lync Server Management Shell :

    Get-CsAdminRole

N’oubliez pas que l’identité (indiquée par Identity) du rôle RBAC (par exemple, CsVoiceAdministrator) correspond à un groupe de sécurité dans le conteneur Utilisateurs des services de domaine Active Directory.

Pour obtenir une liste des applets de commande affectées à un rôle, utilisez une commande similaire à celle-ci :

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

## Affectation d’un rôle RBAC à un utilisateur

Pour affecter un rôle RBAC à un utilisateur, vous devez ajouter ce dernier au groupe de sécurité Active Directory approprié. Par exemple, pour affecter le rôle CsLocationAdministrator à un utilisateur, vous devez ajouter cet utilisateur au groupe CsLocationAdministrator. Pour ce faire, effectuez la procédure suivante :

**Pour affecter un utilisateur à un groupe de sécurité**

1.  En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.

2.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Outils d’administration** , puis sur **Utilisateurs et ordinateurs Active Directory** .

3.  Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur **Utilisateurs** .

4.  Cliquez avec le bouton droit sur le groupe de sécurité **CsLocationAdministrator** , puis cliquez sur **Propriétés** .

5.  Dans la boîte de dialogue **Propriétés** , sous l’onglet **Membres** , cliquez sur **Ajouter** .

6.  Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes** , tapez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe (par exemple, **Ken Myer** ) dans la zone **Entrer les noms des objets à sélectionner** , puis cliquez sur **OK** .

7.  Dans la boîte de dialogue **Propriétés** , cliquez sur **OK** .

Pour vérifier que le rôle RBAC a été affecté, utilisez l’applet de commande [Get-CsAdminRoleAssignment](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAdminRoleAssignment), en indiquant le nom SamAccountName (nom de connexion Active Directory) de l’utilisateur. Par exemple, exécutez cette commande directement depuis Lync Server Management Shell :

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

