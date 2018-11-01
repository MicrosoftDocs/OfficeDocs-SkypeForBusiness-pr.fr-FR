---
title: "Lync Server 2013 : Activ. des util. Lync pour le contrôle d’appel distant"
TOCTitle: Activation des utilisateurs Lync pour le contrôle d’appel distant
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615048(v=OCS.15)
ms:contentKeyID: 49299317
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous pouvez configurer les utilisateurs Lync pour le contrôle d’appel distant en utilisant des stratégies de provisionnement intrabande basées sur le serveur. Vous pouvez gérer les paramètres de provisionnement intrabande à l’aide du Panneau de configuration Lync Server ou de l’interface de ligne de commande Lync Server Management Shell. Ces outils remplacent le composant logiciel enfichable Windows Management Interface (WMI) utilisé pour gérer les paramètres de stratégie de groupe des versions antérieures.

Si vous préférez laisser les utilisateurs configurer leurs propres paramètres de contrôle d’appel distant dans Lync, vous pouvez configurer les paramètres de contrôle d’appel distant pour les utilisateurs sur le serveur sans indiquer les valeurs **URI de serveur de ligne** et **URI de ligne**. Vérifiez que vous communiquez à vos utilisateurs les valeurs **URI de serveur de ligne** et **URI de ligne** appropriées, ainsi que les instructions nécessaires pour configurer ces paramètres. Pour savoir comment configurer manuellement le contrôle d’appel distant dans Lync Server, reportez-vous à « Définir les options et les numéros de téléhone » à l’adresse <http://go.microsoft.com/fwlink/p/?linkid=210132>, dans la documentation du client Lync sur le site web de Microsoft Office.

Si vous avez un déploiement Communications Server 2007 R2 ou Communications Server 2007 existant, les clients Communicator 2007 R2 et Communicator 2007 continueront d’utiliser une stratégie de groupe pendant la migration côte à côte. Cependant, si vous voulez que les paramètres de stratégie s’exécutent sur les clients Lync, vous devez configurer les paramètres de provisionnement intrabande Lync Server équivalents.

> [!NOTE]  
> Pour permettre à un utilisateur d’utiliser le contrôle d’appel distant, vous devez fournir à cet utilisateur un URI de ligne et un URI de serveur de ligne. Tel que décrit dans <a href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Tâches de déploiement du contrôle d’appel distant dans Lync Server 2013</a>, vous devez vérifier que vous utilisez la syntaxe exigée par la passerelle pour ces paramètres.<br />
Vérifiez que le domaine dans l’URI de serveur de ligne est identique au domaine de destination que vous avez spécifié dans le paramètre MatchUri lorsque vous avez configuré l’itinéraire statique vers la passerelle.<br />
L’URI de ligne indique le numéro de téléphone affecté à l’utilisateur au format E.164, avec le préfixe « TEL: » (par exemple, tel:+14255550150). Si vous voulez configurer un numéro de poste, le format est tel:+14255550150;ext=111. Si vous avez précédemment configuré l’URI de ligne de l’utilisateur et si la valeur n’a pas changé, il n’est pas nécessaire de spécifier l’URI de ligne lorsque vous autorisez l’utilisateur à utiliser le contrôle d’appel distant.

## Pour activer le contrôle d’appel distant pour les utilisateurs Lync à l’aide de Management Shell

1.  Connectez-vous à un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou en tant que rôle RBAC (contrôle d’accès basé sur un rôle) auquel vous avez affecté l’applet de commande **Set-CsUser**.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour utiliser l’applet de commande **Set-CsUser** en vue de configurer le contrôle d’accès distant pour un utilisateur Lync activé existant, procédez comme suit :
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Exemple :
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

## Pour configurer des utilisateurs pour le contrôle d’appel distant à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs** .

4.  Dans la zone **Rechercher des utilisateurs** , tapez l’intégralité (ou le début) du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher** .

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.

6.  Dans le menu **Edition** , cliquez sur **Modifier** .

7.  Dans **Téléphoniee** , effectuez l’une des opérations suivantes :
    
      - Pour activer le contrôle d’appel distant en vue d’autoriser l’utilisateur à contrôler ses téléphones PBX depuis Lync 2013 dans le but de passer des appels audio de PC à PC et de PC à téléphone, cliquez sur **Contrôle d’appel distant** . Dans **URI de ligne** , spécifiez le numéro de téléphone de l’utilisateur. Dans **URI de serveur de ligne** , spécifiez l’URI SIP de la passerelle SIP/CSTA.
    
      - Pour activer le contrôle d’appel distant mais désactiver les appels audio de PC à PC et autoriser uniquement l’utilisateur à contrôler ses téléphones PBX à partir de Lync 2013 dans le but de passer des appels audio de PC à téléphone, cliquez sur **Contrôle d’appel distant uniquement** . Dans **URI de ligne** , spécifiez le numéro de téléphone de l’utilisateur. Dans **URI de serveur de ligne** , spécifiez l’URI SIP de la passerelle SIP/CSTA.

8.  Lorsque vous avez terminé, cliquez sur **Valider** .

