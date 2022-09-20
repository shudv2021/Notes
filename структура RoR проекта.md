[[conserns]] это папка в app/controllers в которую можно выносить методы бизнеслогики или другие (напримпер связанные с аутентификацией), чтобы не захламлять контролеры. метыды связанные с отображением лучше выносить в [[decoratoers]] .
Подключение conserns осушествляется как и подключение модулей в app/application_controller (те в абстрактный класс)

Подключение
app/controller/application_controllet:
	include WhatIncluded

app/controllers/conserns/what_included.rb
	module WhatIncluded
	extend ActiveSupport::Concern
		included do
			private
			def method_which_we_need_in_application
				return if @user.name.present?
				@user.name = @user.email.split('@')[0]
			end
		end
	end

Использование

app/controllers/user_controller.rb

def create
	@user=User.new user_params
	 method_which_we_need_in_application
end