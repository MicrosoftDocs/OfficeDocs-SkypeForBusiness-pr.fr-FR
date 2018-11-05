---
title: "Lync Server 2013 : Activ. ou désactiv. de l’accès des utilisateurs distants"
TOCTitle: Activation ou désactivation de l’accès des utilisateurs distants
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182586(v=OCS.15)
ms:contentKeyID: 49298855
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les utilisateurs distants sont des utilisateurs de votre entreprise qui disposent d’une identité Active Directory persistante au sein de l’entreprise. Les utilisateurs distants se connectent souvent à Lync Server en dehors de votre réseau à l’aide d’un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre entreprise. Il s’agit d’employés travaillant à domicile ou en déplacement, ainsi que d’autres travailleurs à distance (par exemple, fournisseurs approuvés pour lesquels des informations d’identification d’entreprise ont été définies). Si vous activez l’accès pour les utilisateurs distants, ceux qui sont pris en charge se connectent via Internet. Ils n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec les utilisateurs internes de Lync Server.

Pour prendre en charge l’accès des utilisateurs distants, vous devez l’activer (pour l’ensemble de votre entreprise). Si vous souhaitez plus tard empêcher temporairement ou définitivement l’accès des utilisateurs distants, vous pouvez le désactiver pour votre entreprise. Suivez la procédure dans cette section pour activer ou désactiver l’accès des utilisateurs distants pour votre entreprise.

> [!NOTE]  
> L’activation de la prise en charge de l’accès des utilisateurs distants spécifie seulement que vos serveurs exécutant le service Edge d’accès prennent en charge les communications avec les utilisateurs distants. Par contre, ces derniers ne peuvent pas participer à la messagerie instantanée ni aux conférences dans l’entreprise tant que vous n’avez pas également configuré au moins une stratégie de gestion de l’utilisation de l’accès des utilisateurs distants. Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet. Pour plus d’informations sur la configuration des stratégies pour l’utilisation de l’accès des utilisateurs distants, reportez-vous à <a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013</a>.

## Pour activer ou désactiver l’accès des utilisateurs distants pour votre entreprise

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe** , puis sur **Configuration du serveur Edge d’accès** .

4.  Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global** , sur **Modifier** , puis sur **Afficher les détails** .

5.  Dans **Modifier la configuration du serveur Edge d’accès** , effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs distants pour votre entreprise, activez la case à cocher **Activer l’accès des utilisateurs distants** .
    
      - Pour désactiver l’accès des utilisateurs distants pour votre entreprise, désactivez la case à cocher **Activer l’accès des utilisateurs distants** .

6.  Cliquez sur **Valider** .

Pour permettre aux utilisateurs distants de se connecter aux serveurs exécutant Lync Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants. Pour plus d’informations, reportez-vous à [Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) dans la documentation de déploiement ou des opérations.

## Activation ou désactivation de l’accès des utilisateurs distants à l’aide des applets de commande Windows PowerShell

Il est possible de gérer l’accès des utilisateurs distants à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration (exécutable depuis le Lync Server 2013 Management Shell ou une session à distance de Windows PowerShell). Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Activer l’accès des utilisateurs distants

  - Pour activer l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## Désactiver l’accès des utilisateurs distants

  - Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

