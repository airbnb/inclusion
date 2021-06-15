task :parse_data_file do
  require 'yaml'
  infractions_file = File.join(__dir__, 'infractions.yml')
  YAML.parse(File.read(infractions_file))
end

# Ensures that each item in infractions.yml has at least one term and alternative.
task :validate_data do
  require 'yaml'
  infractions_file = File.join(__dir__, 'infractions.yml')
  infractions = YAML.load(File.read(infractions_file))
  error_message = ''
  if infractions.any? { |i| i['terms'].nil? || i['terms'].empty? }
    error_message += 'Each infraction must contain at least one term.'
  end
  if infractions.any? { |i| i['alternatives'].nil? || i['alternatives'].empty? }
    error_message += 'Each infraction must contain at least one alternative.'
  end
  raise error_message unless error_message.empty?
end
