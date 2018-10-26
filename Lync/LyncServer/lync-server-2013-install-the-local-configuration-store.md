---
title: 'Lync Server 2013 : Installation du magasin de configurations local'
TOCTitle: Installation du magasin de configurations local
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412874(v=OCS.15)
ms:contentKeyID: 49298601
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation du magasin de configurations local dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-06-27_

Avant d’’effectuer la procédure suivante, veillez à vous connecter au serveur avec un compte utilisateur de domaine à la fois administrateur local et membre du groupe RTCUniversalReadOnlyAdmin.

Pour pouvoir réaliser une opération avec le Assistant Déploiement de Lync Server, le magasin de configurations local doit exister sur un serveur. Il s’agit d’une copie en lecture seule du magasin central de gestion, qui est créé après l’installation locale de SQL Server Express. Le magasin central de gestion proprement dit est ajouté à la base de données SQL Server existante installée sur la base de données compatible serveur Standard Edition ou SQL Server Express.

> [!IMPORTANT]  
> Si vous n’avez pas exécuté auparavant le programme d’installation Lync Server 2013 sur ce serveur, vous serez invité à indiquer l’unité et le chemin d’installation de Lync Server 2013. Vous pourrez effectuer cette installation sur une unité autre que l’unité système, si votre organisation l’exige, ou si vous rencontrez des problèmes d’espace. Vous pouvez simplement paramétrer le chemin de l’emplacement d’installation des fichiers Lync Server dans la boîte de dialogue Installation sur une autre unité disponible. Si vous stockez les fichiers d’installation à cet endroit, y compris OCSCore.msi, les autres fichiers Lync Server 2013 y seront également déployés.

## Pour installer le magasin de configurations local

1.  Sur votre support d’installation, accédez à \\setup\\amd64\\Setup.exe, puis cliquez sur **OK**.

2.  Si vous êtes invité à installer Microsoft Visual C++ 2012 Redistributable, cliquez sur **Oui**.

3.  Dans la page **Emplacement d’installation de Lync Server 2013**, cliquez sur **OK**.

4.  Dans la page **Contrat de Licence Utilisateur Final**, passez en revue les termes du contrat de licence, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK** pour pouvoir continuer.

5.  Dans la page Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server** .

6.  Dans la page **Lync Server 2013**, en regard de **Étape 1 : Installer le magasin de configurations local** , cliquez sur **Exécuter** .

7.  Dans la page **Installer le magasin de configurations local** , assurez-vous que l’option **Récupérer directement à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant** .

8.  Cliquez sur **Terminer** une fois l’installation terminée.

