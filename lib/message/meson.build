## Copyright (C) 2021 Dirk-Jan C. Binnema <djcb@djcbsoftware.nl>
##
## This program is free software; you can redistribute it and/or modify
## it under the terms of the GNU General Public License as published by
## the Free Software Foundation; either version 3 of the License, or
## (at your option) any later version.
##
## This program is distributed in the hope that it will be useful,
## but WITHOUT ANY WARRANTY; without even the implied warranty of
## MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
## GNU General Public License for more details.
##
## You should have received a copy of the GNU General Public License
## along with this program; if not, write to the Free Software Foundation,
## Inc., 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301, USA.


lib_mu_message=static_library(
  'mu-message',
  [
    'mu-message.cc',
    'mu-message.hh',
    'mu-message-part.cc',
    'mu-message-part.hh',
    'mu-contact.hh',
    'mu-contact.cc',
    'mu-document.cc',
    'mu-document.hh',
    'mu-fields.hh',
    'mu-fields.cc',
    'mu-flags.hh',
    'mu-flags.cc',
    'mu-priority.hh',
    'mu-priority.cc',
    'mu-mime-object.cc',
    'mu-mime-object.hh'
  ],
  dependencies: [
    glib_dep,
    gmime_dep,
    xapian_dep,
    config_h_dep,
    lib_mu_utils_dep],
  install: false)

lib_mu_message_dep = declare_dependency(
  link_with: lib_mu_message,
  dependencies: [ xapian_dep, gmime_dep ],
  include_directories:
    include_directories(['.', '..']))

#
# tests
#

test('test-contact',
     executable('test-contact',
		'mu-contact.cc',
		install: false,
		cpp_args: ['-DBUILD_TESTS'],
		dependencies: [glib_dep, gmime_dep, lib_mu_message_dep]))

test('test-document',
     executable('test-document',
		'mu-document.cc',
		install: false,
		cpp_args: ['-DBUILD_TESTS'],
		dependencies: [glib_dep, gmime_dep, lib_mu_message_dep]))

test('test-fields',
     executable('test-fields',
		'mu-fields.cc',
		install: false,
		cpp_args: ['-DBUILD_TESTS'],
		dependencies: [glib_dep, gmime_dep, lib_mu_message_dep]))

test('test-flags',
     executable('test-flags',
		'mu-flags.cc',
		install: false,
		cpp_args: ['-DBUILD_TESTS'],
		dependencies: [glib_dep, gmime_dep, lib_mu_message_dep]))

test('test-message',
     executable('test-message',
		'mu-message.cc',
		install: false,
		cpp_args: ['-DBUILD_TESTS'],
		dependencies: [glib_dep, gmime_dep, lib_mu_message_dep]))

test('test-priority',
     executable('test-priority',
		'mu-priority.cc',
		install: false,
		cpp_args: ['-DBUILD_TESTS'],
		dependencies: [glib_dep, gmime_dep, lib_mu_message_dep]))