---
title: 'Lync Server 2013 : Délégation des autorisations de configuration'
TOCTitle: Délégation des autorisations de configuration
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412735(v=OCS.15)
ms:contentKeyID: 49298330
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Délégation des autorisations de configuration dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-05_

Si vous ne souhaitez pas accorder d’appartenance au groupe des administrateurs du domaine à des utilisateurs ou des groupes qui déploient Lync Server 2013, vous pouvez permettre aux membres du groupe RTCUniversalServerAdmins d’exécuter l’applet de commande **Enable-CsTopology**  Windows PowerShell sur les serveurs exécutant Lync Server 2013. Par défaut, les membres du groupe RTCUniversalServerAdmins group n’ont pas la possibilité d’exécuter cette applet de commande. Vous accordez des droits d’administrateurs et des autorisations pour exécuter **Enable-CsTopology** sur des serveurs exécutant Lync Server à l’aide de l’applet de commande **Grant-CsSetupPermission** et en spécifiant une unité d’organisation où sont situés les objets ordinateur du serveur exécutant Lync Server 2013.

La préparation du domaine qui a lieu lorsque vous installez Lync Server n’ajoute pas automatiquement les autorisations qui permettent aux membres du groupe RTCUniversalServerAdmins d’exécuter l’applet de commande Enable-CsTopology. Cela signifie que, par défaut, vous devez être administrateur de domaine pour activer une topologie. Pour accorder aux membres du groupe RTCUniversalServerAdmins le droit d’activer une topologie, vous devez exécuter l’applet de commande Grant-CsSetupPermissions. En outre, vous devrez exécuter cette applet de commande sur chaque conteneur Active Directory qui héberge des ordinateurs exécutant Lync Server.

Souvenez-vous que cette applet de commande n’accorde des autorisations qu’au groupe RTCUniversalServerAdmins. Vous ne pouvez pas l’utiliser pour accorder des autorisations à d’autres groupes de sécurité ou à des utilisateurs individuels.

> [!NOTE]  
> <strong>Enable-CsTopology</strong> est l’applet de commande principale pour permettre aux membres du groupe RTCUniversalServerAdmins de configurer et de déployer Lync Server 2013.

## Pour ajouter la possibilité d’exécuter Enable-CsTopology au groupe RTCUniversalServerAdmins

1.  Ouvrez une session sur un serveur en tant que membre du groupe des administrateurs du domaine sur lequel l’utilisateur délégué exécutera **Enable-CsTopology**.

2.  Ouvrez Lync Server 2013 Management Shell. Lync Server 2013 Management Shell est installé automatiquement sur chaque serveur frontal ou tout ordinateur sur lequel les outils d’administration de Lync Server 2013 sont installés. Pour plus d’informations sur Lync Server 2013 Management Shell, reportez-vous à [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md) dans la documentation des opérations.

3.  Exécutez l’applet de commande suivante à partir de Lync Server 2013 Management Shell :
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    > [!NOTE]  
    > S’il ne s’agit pas d’une unité d’organisation de niveau supérieur, vous devez fournir le nom de domaine complet.    
    
    
    Dans l’exemple suivant, l’unité d’organisation est « Lync Servers », située dans le domaine contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

