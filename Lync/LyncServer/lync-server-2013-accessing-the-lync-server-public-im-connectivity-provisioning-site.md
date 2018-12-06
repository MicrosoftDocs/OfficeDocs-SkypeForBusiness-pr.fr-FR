---
title: "Lync Server 2013 : accès au site d’approv. de connectivité PIC de Lync Server"
TOCTitle: Accès au site d’approvisionnement de connectivité PIC de Lync Server
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn440174(v=OCS.15)
ms:contentKeyID: 59602874
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Accès au site d’approvisionnement de connectivité PIC de Lync Server à partir de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-03-09_

Le processus d'approvisionnement de la connectivité Lync-Skype a changé par rapport aux méthodes d'approvisionnement PIC précédentes. Ce processus d'approvisionnement peut nécessiter jusqu'à trente jours. Nous vous recommandons de commencer par démarrer ce processus, avant d'effectuer les étapes restantes de ce document. Une fois le processus d'approvisionnement Lync-Skype terminé pour votre compte, ce dernier est activé et vos utilisateurs éligibles sont activés pour la connectivité PIC.

### Pour approvisionner la connectivité Lync-Skype, vous avez besoin des informations suivantes :

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol><li><p>Numéro de contrat Microsoft</p></li><li><p>Nom de domaine complet (FQDN) du service Edge d'accès Edge</p></li><li><p>Domaine(s) SIP (Session Initiation Protocol)</p></li><li><p>Noms complets (FQDN) supplémentaires éventuels du service Edge d'accès</p></li><li><p>Coordonnées</p></li></ol></td>
</tr>
<tr class="even">
<td><ol><li><p>Numéro de contrat Microsoft</p></li><li><p>Nom de domaine complet (FQDN) du service Edge d'accès Edge</p></li><li><p>Domaine(s) SIP (Session Initiation Protocol)</p></li><li><p>Noms complets (FQDN) supplémentaires éventuels du service Edge d'accès</p></li><li><p>Coordonnées</p></li></ol></td>
</tr>
</tbody>
</table>


### Pour lancer le processus d'approvisionnement pour la connectivité Lync-Skype :

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol><li><p>Connectez-vous au site <strong>https://pic.lync.com</strong> à l’aide de votre identifiant Microsoft Windows Live ID.</p></li><li><p>Sélectionnez le type de contrat de licence Microsoft.</p></li>
> <li><p>Activez la case à cocher indiquant que vous avez lu et accepté les droits d'utilisation du produit pour Lync Server.</p></li>
> <li><p>Dans la page <strong>Émettre une demande d’approvisionnement</strong>, cliquez sur le lien approprié pour émettre une demande d’approvisionnement :</p></li>
> <li><p>Dans la page <strong>Indiquer les informations d’approvisionnement</strong> entrez le <strong>nom complet du service Edge d’accès</strong>. Par exemple, <strong>accessedge.contoso.com</strong>.</p></li>
> <li><p>Entrez au moins un nom de domaine SIP, puis cliquez sur <strong>Ajouter</strong>.</p>
<div>

> [!IMPORTANT]  
> Au moins un serveur Edge d'accès et un domaine SIP sont requis pour effectuer le processus d'approvisionnement. Le domaine SIP et le serveur Edge d'accès doivent être actifs, en état de fonctionnement et accessibles sur le réseau.
</div></li><li><p>Dans la liste des <strong>fournisseurs de service de messagerie instantanée publique</strong>, sélectionnez <strong>Skype,</strong> et cliquez sur <strong>Suivant</strong> pour ajouter des coordonnées, puis envoyez la demande d’approvisionnement.</p></li></ol></td>
</tr>
<tr class="even">
<td><ol><li><p>Connectez-vous au site <strong>https://pic.lync.com</strong> à l’aide de votre identifiant Microsoft Windows Live ID.</p></li><li><p>Sélectionnez le type de contrat de licence Microsoft.</p></li>
> <li><p>Activez la case à cocher indiquant que vous avez lu et accepté les droits d'utilisation du produit pour Lync Server.</p></li>
> <li><p>Dans la page <strong>Émettre une demande d’approvisionnement</strong>, cliquez sur le lien approprié pour émettre une demande d’approvisionnement :</p></li>
> <li><p>Dans la page <strong>Indiquer les informations d’approvisionnement</strong> entrez le <strong>nom complet du service Edge d’accès</strong>. Par exemple, <strong>accessedge.contoso.com</strong>.</p></li>
> <li><p>Entrez au moins un nom de domaine SIP, puis cliquez sur <strong>Ajouter</strong>.</p>
<div>

> [!IMPORTANT]  
> Au moins un serveur Edge d'accès et un domaine SIP sont requis pour effectuer le processus d'approvisionnement. Le domaine SIP et le serveur Edge d'accès doivent être actifs, en état de fonctionnement et accessibles sur le réseau.
</div></li><li><p>Dans la liste des <strong>fournisseurs de service de messagerie instantanée publique</strong>, sélectionnez <strong>Skype,</strong> et cliquez sur <strong>Suivant</strong> pour ajouter des coordonnées, puis envoyez la demande d’approvisionnement.</p></li></ol></td>
</tr>
</tbody>
</table>


Une fois la demande d'approvisionnement envoyée, l'activation du compte et des utilisateurs pour la connectivité PIC peut prendre jusqu'à 30 jours.

## Activation de la fédération et de la connectivité PIC (Public IM Connectivity)

Une fois la demande d'approvisionnement transmise, vous pouvez vous concentrer sur l'environnement Lync Server et les tâches d'administration nécessaires à la configuration de la connectivité Lync-Skype. Cette section suppose que l'administrateur Lync Server a déployé Lync Server et configuré l'accès externe. Pour plus d'informations sur la configuration de l'accès externe pour Lync Server, voir « Planification de l'accès des utilisateurs externes » à l'adresse [http://go.microsoft.com/fwlink/p/?LinkID=273772](http://go.microsoft.com/fwlink/p/?linkid=273772) et « Déploiement de l'accès des utilisateurs externes » à l'adresse [http://go.microsoft.com/fwlink/p/?LinkID=27378](http://go.microsoft.com/fwlink/p/?linkid=27378).

Pour préparer l'environnement Lync Server pour la connectivité Lync-Skype, l'administrateur Lync Server doit effectuer les trois tâches suivantes :

## 1\. Configurer la fédération et la connectivité PIC

La fédération est requise pour permettre aux utilisateurs Skype de communiquer avec les utilisateurs Lync dans votre organisation. La connectivité PIC (Public IM Connectivity) est une classe de fédération. Elle doit être configurée pour permettre à vos utilisateurs Lync de communiquer avec les utilisateurs Skype. La fédération et la connectivité PIC sont configurées à l'aide du panneau de configuration Lync Server (affiché ci-dessous).

> [!IMPORTANT]  
> La fédération PIC n'est plus prise en charge par Live Communication Server 2005 SP1 ou Office Communications Server 2007. Les plateformes prises en charge pour la fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.

## 2\. Configurer au moins une stratégie pour la prise en charge de l'accès des utilisateurs fédérés

À l'aide du panneau de configuration Lync Server, l'administrateur doit configurer une ou plusieurs stratégies d'accès des utilisateurs externes pour contrôler la possibilité pour les utilisateurs Skype de collaborer avec les utilisateurs Lync Server internes.

## 3\. Configurer le paramètre de fournisseur PIC Skype pour Lync

À l'aide de Lync Server Management Shell, l'administrateur doit configurer la stratégie de client Lync pour afficher Skype comme fournisseur PIC supplémentaire.

> [!NOTE]  
> Les utilisateurs du service PIC ne peuvent pas participer à des sessions de messagerie instantanée ou des conférences dans votre organisation tant que vous n'avez pas configuré au moins une stratégie (étape 2 de cette procédure) pour prendre en charge la connectivité PIC.<br />
Pour configurer la fédération et la connectivité PIC, voir « Activation ou désactivation de la fédération et de la connectivité PIC (Public IM Connectivity) » à l'adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=306063">http://go.microsoft.com/fwlink/p/?LinkId=306063</a>.<br />
Pour configurer au moins une stratégie pour prendre en charge l'accès des utilisateurs fédérés, voir « Configuration des stratégies de contrôle d'accès des utilisateurs publics » à l'adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=306064">http://go.microsoft.com/fwlink/p/?LinkId=306064</a>.

1.  À partir d'un serveur frontal Lync Server, ouvrez Lync Server Management Shell.

2.  Exécutez les deux commandes suivantes :
    
      - Remove-CsPublicProvider -Identity Messenger
    
      - New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger\_16x16.png" -VerificationLevel 2 -Enabled 1

3.  À partir d’un client Lync, vous pouvez désormais sélectionner Skype en tant que fournisseur PIC, et ajouter un client Skype en spécifiant son compte Microsoft. De plus, un utilisateur Skype qui a effectué la fusion et qui est connecté à partir de son compte Microsoft peut envoyer une demande de contact aux utilisateurs Lync. Pour plus d’informations sur les comptes Microsoft, voir [Qu'est-ce qu’un compte Microsoft ?](https://support.skype.com/fr/faq/fa12059/what-is-a-microsoft-account). Pour plus d’informations concernant l’ajout de clients à Lync, voir [Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Pour plus d'informations sur la modification des fournisseurs hébergés, voir « Création ou modification de fournisseurs fédérés SIP hébergés » à l'adresse [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).

Cette procédure termine les tâches d'administration qui doivent être effectuées sur le serveur. Vous pouvez à présent utiliser la connectivité Lync-Skype.

## Ressources supplémentaires

[Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Provisioning guide for Lync-Skype connectivity in Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

